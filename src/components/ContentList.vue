<script setup>
    defineProps(['list']);
</script>

<template>
    <ul>
        <li v-for="(item, index) in list" :key="index">{{ item.title }}</li>
    </ul>
</template>

<style scoped>
</style>