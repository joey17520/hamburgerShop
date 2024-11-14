<template>
    <!-- 所有汉堡的容器 -->
    <div class="meals">
        <Meal :desc="$attrs.desc" v-for="item in props.meals" :meal="item"></Meal>
        <h2 v-if="!props.meals || props.meals.length === 0">没有找到相关商品!</h2>
    </div>
</template>

<script setup>
import Meal from './Meal.vue';

const props = defineProps(["meals"])

</script>

<style scoped>
.meals {
    padding-bottom: 150rem;
    height: calc(100vh - 120rem);
    overflow: auto;
}

.meals h2 {
    display: flex;
    justify-content: center;
    align-items: center;
    font-size: 60rem;
    color: rgb(147, 147, 147);
}
</style>