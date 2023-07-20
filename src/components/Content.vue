<script setup>
    import ContentTitle from './ContentTitle.vue';
    import ContentList from './ContentList.vue';

    defineProps(['list']);
</script>

<template>
    <ContentTitle />

    <ContentList :list="list" />
</template>

<style scoped>
</style>