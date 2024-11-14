<template>
    <Checkout @close="showCheckout = false" :is-show="showCheckout"></Checkout>
    <CartDetails :is-show="showDetails" @hide="showDetails = false"></CartDetails>

    <div class="cart-bar">
        <div class="cart-bag">
            <img :src="cartBag" alt="">
            <span v-show="meals.totalCount > 0" class="total-count">{{ meals.totalCount }}</span>
        </div>

        <div class="total-amount">
            <p v-show="meals.totalCount <= 0" class="no-goods">未选购商品</p>
            <p @click="showDetails = true" v-show="meals.totalCount > 0" class="has-goods">{{ meals.amount }}</p>
        </div>

        <button @click="showCheckout = meals.totalCount > 0" class="checkout-btn">结算</button>
    </div>
</template>

<script setup>
import { useMealsStore } from "@/store/meals";
import cartBag from "../../assets/bag.png"
import { ref } from "vue";
import CartDetails from "./CartDetails.vue";
import Checkout from "../checkout/Checkout.vue";

const meals = useMealsStore()
const showDetails = ref(false)
const showCheckout = ref(false)

</script>

<style scoped>
.cart-bar {
    width: 710rem;
    height: 100rem;
    position: fixed;
    left: 0;
    right: 0;
    margin: 0 auto;
    margin: 0 auto;
    background-color: rgb(58, 58, 58);
    bottom: 40rem;
    border-radius: 60rem;
    z-index: 9999;
}

.cart-bag {
    position: absolute;
    bottom: -10rem;
    width: 100rem;
}

.total-count {
    width: 40rem;
    height: 40rem;
    text-align: center;
    line-height: 35rem;
    position: absolute;
    right: -20rem;
    color: aliceblue;
    font-size: 30rem;
    font-weight: bold;
    background-color: red;
    border-radius: 50%;
}

.total-amount {
    margin-left: 140rem;
    line-height: 100rem;
}

.no-goods, .has-goods {
    font-size: 36rem;
    font-weight: bold;
    color: rgb(148, 148, 148);
}

.has-goods {
    color: #fff;
    font-size: 30rem;
}

.has-goods::before {
    content: "￥";
}

.checkout-btn {
    position: absolute;
    top: 0;
    right: 0;
    width: 200rem;
    height: 100%;
    border-radius: 60rem;
    border: none;
    background-color: rgb(248, 188, 0);
    font-size: 36rem;
    font-weight: bold;
}
</style>