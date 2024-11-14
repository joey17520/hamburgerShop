<template>
    <Mask>
        <div class="dialog">
            <p class="msg"><slot></slot></p>
            <div class="btn">
                <button @click="$emit('hide')" class="cancel">取消</button>
                <button @click="() => {
                    $emit('clear')
                    $emit('hide')
                }" class="ok">确认</button>
            </div>
        </div>
    </Mask>
</template>

<script setup>
import Mask from './Mask.vue';

const emits = defineEmits(["clear"])

</script>

<style scoped>
.dialog {
    position: absolute;
    top: 0;
    bottom: 0;
    left: 0;
    right: 0;
    width: 700rem;
    height: 400rem;
    background-color: #fff;
    border-radius: 40rem;
    margin: auto;
}

.msg {
    font-size: 40rem;
    font-weight: bold;
    height: 260rem;
    text-align: center;
    line-height: 260rem;
}

.btn {
    display: flex;
    justify-content: space-evenly;
    margin-top: 25rem;
}

button {
    width: 300rem;
    height: 80rem;
    border-radius: 40rem;
    border: 1px solid #000;
    background-color: #fff;
}

.ok {
    background-color: rgb(248, 188, 0);;
}
</style>