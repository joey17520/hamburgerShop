<template>
    <!-- Teleport可以将组件渲染到页面的指定位置 -->
    <teleport to="#cart">
        <div :="$attrs" @click.self="$emit('hide')" class="mask" v-show="props.isShow">
            <slot></slot>
        </div>
    </teleport>
</template>

<script setup>

const props = defineProps(["isShow"])
const emits = defineEmits(["hide"])

</script>

<style scoped>
.mask {
    position: fixed;
    top: 0;
    bottom: 0;
    left: 0;
    right: 0;
    background-color: rgba(0, 0, 0, 0.4);
    z-index: 9999;
}
</style>