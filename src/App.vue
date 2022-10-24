<script>
export default {
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
    <div>
        <h3>{{ count }}</h3>
        <section class="button__section">
            <button @click="increment">Plus</button>
            <button @click="decrement">Minus</button>
            <button @click="cleanCount">Zeruj</button>
        </section>
    </div>
</template>

<style lang="scss" scoped>
div {
    display: flex;
    flex-direction: column;
    justify-content: center;
    align-items: center;
    gap: 1rem;

    h3 {
        font-size: 40px;
    }
}

.button__section {
    display: flex;
    gap: 1rem;
}
</style>