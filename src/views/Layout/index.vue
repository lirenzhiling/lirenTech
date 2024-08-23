
<template>
    <LayoutFixed/>
    <LayoutNav/>
    <LayoutHeader/>
    <!-- 添加Key 破坏复用机制 强制销毁重建 -->
    <!-- <RouterView :key="$route.fullPath"/> -->
    <RouterView/>
    <LayoutFooter/>
</template>
<script setup>
import LayoutHeader from './components/LayoutHeader.vue';
import LayoutNav from './components/LayoutNav.vue';
import LayoutFooter from './components/LayoutFooter.vue';
import LayoutFixed from "./components/LayoutFixed.vue";

// 触发获取导航列表的action
import { useCategoryStore } from "@/stores/category";
import { onMounted } from "vue";

const categoryStore=useCategoryStore()

onMounted(()=>categoryStore.getCategory())
</script>
<style scoped></style>