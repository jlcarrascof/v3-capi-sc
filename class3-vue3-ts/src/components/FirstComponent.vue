<script lang="ts" setup>
    import { ref, onBeforeMount, onMounted, onBeforeUpdate, onUpdated, onBeforeUnmount, onUnmounted } from 'vue';

    // Reactive State
    const message = ref<string>('Hello');

    // Refs
    const mainElement = ref<HTMLElement | null>(null);

    // Methods 
    const changeMessage = () => {
        message.value = 'Hello changed!'
    }
</script>

<template>
    <h1>First Component</h1>
</template>

<style scoped>
    h1 { color: #2c3e50; }
</style>