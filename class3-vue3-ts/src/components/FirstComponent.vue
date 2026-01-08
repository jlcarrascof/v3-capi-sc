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

    onBeforeMount(() => {
        console.log("I'm in onBeforeMount() ....")
        console.log(mainElement.value)
    })

    onMounted(() => {
        console.log("I'm in onMounted() ....")
        console.log(mainElement.value)
    })

    onBeforeUpdate(() => {
        console.log("I'm in onBeforeUpdate() ....")
        console.log(mainElement.value)
    })

    onUpdated(() => {
        console.log("I'm in onUpdated() ....")
        console.log(mainElement.value)
    })

    onBeforeUnmount(() => {
        console.log("I'm in onBeforeUnmount() ....")
        console.log(message.value)
    })

    onUnmounted(() => {
        console.log("I'm in onUnmounted() ....")
        console.log(message.value)
    })
</script>

<template>
    <h1 ref="mainElement">{{ message }}</h1>
    <button @click="changeMessage">Change Message</button>
    <!-- In Vue 3, $destroy() doesn't exist; component destruction is handled with v-if in the parent component. -->
    <button @click="destroyComponent">Destroy Component</button>
</template>

<style scoped>
    h1 { color: #2c3e50; }
</style>