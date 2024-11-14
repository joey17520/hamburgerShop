<template>
    <div class="counter">
        <template v-if="props.meal.count > 0">
            <button @click="meals.subMealToCart(props.meal)" class="sub"><i class="ri-subtract-line"></i></button>
            <span class="count">{{ props.meal.count }}</span>
        </template>
        <button @click="meals.addMealToCart(props.meal)" class="add"><i class="ri-add-line"></i></button>
    </div>
</template>

<script setup>
import { useMealsStore } from '@/store/meals';

const meals = useMealsStore()
const props = defineProps(["meal"])


</script>

<style scoped>
.counter {
    display: flex;
    align-items: center;
}

.sub,
.add {
    display: flex;
    justify-content: center;
    align-items: center;
    width: 32rem;
    height: 32rem;
    background-color: rgb(234, 178, 0);
    border: none;
    border-radius: 50%;
    font-size: 32rem;
    font-weight: bold;
}

.sub {
    background-color: #fff;
    border: 1px #000 solid;
}

.count {
    font-size: 30rem;
    margin: 0 15rem;
}
</style>