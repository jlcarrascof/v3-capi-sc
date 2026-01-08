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

    // Destroy() Vue 2 ... simulation
    const destroyComponent = () => {
        console.log('Simulating component destruction: in Vue 3 this is handled with v-if in the parent component.');
    }

    // Life Cycle
    // created/beforeCreate → logic goes directly in setup()
    console.log("I'm in setup() (equiv. created)")
    console.log(message.value)


</script>

<template>
    <h1>First Component</h1>
</template>

<style scoped>
    h1 { color: #2c3e50; }
</style>