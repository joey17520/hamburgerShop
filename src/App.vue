<template>
  <div>
    <MealFilter></MealFilter>
    <Meals :desc="true" :meals="meals.filterMeals"></Meals>
    <CartBar></CartBar>
  </div>
</template>

<script setup>
import CartBar from './components/Carts/CartBar.vue';
import MealFilter from './components/MealFilter/MealFilter.vue';
import Meals from './components/Meals/Meals.vue';
import { useMealsStore } from './store/meals';

const meals = useMealsStore()

</script>

<style scoped>

</style>