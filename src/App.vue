<script>
export default {
    data() {
        return {
            count: 0
        }
    }
}
</script>

<template>
    <h1>sierant.me</h1>
    <div>
        <button @click="count++">Plus</button>
        <h3>{{ count }}</h3>
        <button @click="count--">Minus</button>
    </div>
</template>

<style scoped>
div {
    display: flex;
    gap: 1rem;
}
</style>