<script>
export default {
    name: 'Counting',
    data() {
        return {
            count: 0
        }
    },
    methods: {
        increment() {
            this.count += 1;
        },
        decrement() {
            this.count -= 1;
        },
        cleanCount() {
            this.count = 0;
        }
    }
}
</script>

<template>
    <h1>sierant.me</h1>
    <h3>Counting</h3>
    <div>
        <h3 class="count">{{ count }}</h3>
        <section class="button__section">
            <button @click="increment">Plus</button>
            <button @click="decrement">Minus</button>
            <button @click="cleanCount">Zeruj</button>
        </section>
    </div>
</template>

<style lang="scss" scoped>
.count {
    font-size: 40px;
}

.button__section {
    display: flex;
    gap: 1rem;
}
</style>