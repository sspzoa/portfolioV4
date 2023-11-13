<script setup lang="ts">
import Meal from "~/components/Dimigo/Meal.vue";
import Schedule from "~/components/Dimigo/Schedule.vue";
import Order from "~/components/Dimigo/Order.vue";
</script>

<template>
  <div class="container">
    <Meal/>
    <div class="row">
      <Schedule/>
      <Order/>
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
  gap: 3rem;
}

.row {
  width: 100%;
  max-width: 70rem;
  display: flex;
  flex-direction: row;
  gap: 3rem;
  align-items: flex-start;
}
</style>
