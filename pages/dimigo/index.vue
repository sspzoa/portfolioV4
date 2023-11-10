<script setup lang="ts">
import {onMounted, ref} from 'vue';
import {format} from 'date-fns';

const mealData = ref({
  breakfast: '',
  lunch: '',
  dinner: ''
});

const reformatMeal = (meal: string) => {
  return meal.split('/').map(item => `- ${item.trim()}`).join('\n');
};

onMounted(async () => {
  const currentDate = format(new Date(), 'yyyy-MM-dd');
  const response = await fetch(`https://디미고급식.com/api/${currentDate}`);
  if (response.ok) {
    const data = await response.json();
    if (data.status === 'success') {
      mealData.value.breakfast = reformatMeal(data.meal.breakfast);
      mealData.value.lunch = reformatMeal(data.meal.lunch);
      mealData.value.dinner = reformatMeal(data.meal.dinner);
    }
  }
});
</script>

<template>
  <div class="container">
    <div class="schedule">
      <h1>Schedule</h1>
      <div class="box"></div>
    </div>
    <div class="meal">
      <h1>Meal</h1>
      <div class="box">
        <div class="section">
          <h1>Breakfast</h1>
          <p class="mealSection" id="breakfast">{{ mealData.breakfast }}</p>
        </div>
        <div class="section">
          <h1>Lunch</h1>
          <p class="mealSection" id="lunch">{{ mealData.lunch }}</p>
        </div>
        <div class="section">
          <h1>Dinner</h1>
          <p class="mealSection" id="dinner">{{ mealData.dinner }}</p>
        </div>
      </div>
    </div>
  </div>
</template>

<style scoped>
.container {
  padding: 6rem 0;
  display: flex;
  flex-direction: column;
  justify-content: center;
  align-items: center;
  gap: 5rem;
}

.meal, .schedule {
  display: flex;
  flex-direction: column;
  justify-content: center;
  align-items: center;
  gap: 2rem;
}

.section {
  display: flex;
  flex-direction: column;
  gap: 1rem;
}

.mealSection {
  white-space: pre-wrap;
}

.meal p {
  line-height: 2.5rem;
}

.box {
  width: 70rem;
  padding: 2rem;
  background-color: var(--box-color);
  border-radius: 1rem;
  display: grid;
  grid-template-columns: repeat(3, 1fr);
  grid-gap: 1rem;
}
</style>
