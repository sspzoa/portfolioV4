<script setup lang="ts">
import { ref, computed, onMounted } from 'vue';

const lunchCycle = [1, 3, 4, 2, 5, 6];
const dinnerCycle = [6, 5, 2, 4, 3, 1];
const startDate = new Date('2023-11-20');

const calculateOrder = (start, cycle) => {
  const today = new Date();
  const dayDifference = Math.floor((today - start) / (1000 * 60 * 60 * 24));
  const cycleLength = cycle.length;
  const completedCycles = Math.floor(dayDifference / cycleLength);
  const positionInCycle = dayDifference % cycleLength;
  return [...cycle.slice(positionInCycle), ...cycle.slice(0, positionInCycle)];
};

const lunchOrder = ref([]);
const dinnerOrder = ref([]);

const formatOrder = (order) => {
  return order.reduce((acc, curr, index, array) => {
    if (index % 2 === 0) {
      let pair = `${curr}`;
      if (index + 1 < array.length) {
        pair += `, ${array[index + 1]}`;
      }
      acc.push(pair);
    }
    return acc;
  }, []).join(' → ');
};

const formattedLunchOrder = computed(() => formatOrder(lunchOrder.value));
const formattedDinnerOrder = computed(() => formatOrder(dinnerOrder.value));

onMounted(() => {
  lunchOrder.value = calculateOrder(startDate, lunchCycle);
  dinnerOrder.value = calculateOrder(startDate, dinnerCycle);
});
</script>


<template>
  <div class="orderContainer">
    <h1>Order</h1>
    <div class="box">
      <div class="section">
        <h1>Lunch</h1>
        <h2>{{ formattedLunchOrder }}</h2>
      </div>
      <div class="section">
        <h1>Dinner</h1>
        <h2>{{ formattedDinnerOrder }}</h2>
      </div>
    </div>
  </div>
</template>

<style scoped>
.orderContainer {
  flex: 1;
  display: flex;
  flex-direction: column;
  justify-content: center;
  align-items: center;
  gap: 2rem;
}
.box {
  width: 100%;
  padding: 2rem;
  background-color: var(--box-color);
  border-radius: 1rem;
display: flex;
flex-direction: column;
gap: 3rem;
}
.section {
display: flex;
flex-direction: column;
gap: 1.5rem;
}
h2 {
  font-weight: normal;
text-align: center;
}
</style>
