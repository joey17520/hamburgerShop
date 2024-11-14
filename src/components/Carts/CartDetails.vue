<template>
    <Mask style="z-index: 999;">
        <Dialog @clear="clearHandler" @hide="showDialog = false" :is-show="showDialog">确认操作吗？</Dialog>

        <div class="cart-details">
            <div class="header">
                <h3>购物车详情</h3>
                <a href="javascript:;" @click="showDialog = true">
                    <i class="ri-delete-bin-line"></i>
                    清空购物车
                </a>
            </div>
            <Meals :desc="false" :meals="meals.cartMeals"></Meals>
        </div>
    </Mask>
</template>

<script setup>
import { useMealsStore } from '@/store/meals';
import Meals from '../Meals/Meals.vue';
import Mask from '../UI/Mask.vue';
import Dialog from '../UI/Dialog.vue';
import { ref } from 'vue';

const meals = useMealsStore()
const showDialog = ref(false)
const emits = defineEmits()

const clearHandler = () => {
    /**
     * 1、  清空购物车
     * 2、  关闭对话框Dialog
     * 3、  关闭购物车详情CartDetails
     */
    meals.clearCart()
    emits("hide")
}
</script>

<style scoped>

.cart-details {
    position: absolute;
    bottom: 0;
    width: 750rem;
    background-color: #fff;
    border-top-left-radius: 40rem;
    border-top-right-radius: 40rem;
}

.meals {
    padding-top: 40rem;
    height: auto;
    max-height: calc(280rem * 4);
}

.header {
    background-color: #fff;
    border-top-left-radius: 40rem;
    border-top-right-radius: 40rem;
    display: flex;
    justify-content: space-between;
    padding: 20rem 40rem;
    font-size: 26rem;
}

.header a {
    color: #9f9f9f;
    display: flex;
    align-items: center;
}

.header i {
    font-size: 26rem;
    margin-right: 10rem;
}
</style>