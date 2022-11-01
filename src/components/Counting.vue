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
  <section class="counting__section">
      <h3>Counting</h3>
      <h3 class="count">{{ count }}</h3>
      <section class="button__section">
        <button @click="increment" class="count__button">Plus</button>
        <button @click="decrement" class="count__button">Minus</button>
        <button @click="cleanCount" class="count__button">Zeruj</button>
      </section>
  </section>
</template>

<style lang="scss" scoped>
.counting__section {
  width: 100%;
  background-color: #42b883;
  color: #2c3e50;
  padding: 3rem;
  display: flex;
  flex-direction: column;
  justify-content: center;
  align-items: center;
}
h3 {
    font-size: 40px;
}
.count__button {
  padding: 1rem 2rem;
  border: 1px solid #42b883;
  background-color: #35495e;
  color: whitesmoke;
  cursor: pointer;
}
.button__section {
    display: flex;
  flex-wrap: wrap;
}
</style>