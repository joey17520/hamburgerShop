<template>
    <div class="filter">
        <div class="filter-inner">
            <input v-model="meals.keyword" class="filter-input" type="text" placeholder="请输入关键字">
            <i class="ri-search-line"></i>
        </div>
    </div>
</template>

<script setup>
import { useMealsStore } from '@/store/meals';


const meals  = useMealsStore()

</script>

<style scoped>
.filter {
    padding: 20rem 40rem;
    border-bottom: 1px solid #e6e6e6;
}

.filter-inner {
    display: flex;
    align-items: center;
    height: 80rem;
    position: relative;
}

.filter-input {
    background-color: rgb(242, 242, 242);
    border: none;
    outline: none;
    width: 100%;
    height: 100%;
    border-radius: 40rem;
    padding: 0 60rem 0 80rem;
}

.filter-inner i {
    position: absolute;
    left: 20rem;
    color: rgb(184, 184, 184);
    font-size: 50rem;
}
</style>