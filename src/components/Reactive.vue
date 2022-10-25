<template>
  <section class="reactive_section">
    <button @click="makeOrder" class="reactive__button">Check func</button>
    <section class="reactive__details">
      <h3>Price: {{ price }}</h3>
      <h4>Quantity: {{ quantity }}</h4>
      <h4>Total price: {{ totalPrice }}</h4>
      <h4>Tax: {{ tax }}</h4>
    </section>
  </section>
</template>

<script>
import { reactive, toRefs } from 'vue';
export default {
  name: "Reactive",
  setup() {
    const state = reactive({
      quantity: 0,
      price: 50,
      totalPrice: 0,
      tax: 0,
    });
    function makeOrder() {
      state.quantity++
      state.totalPrice = state.price * state.quantity;
      state.tax = state.totalPrice * 0.23;
    }
    return { makeOrder, ...toRefs(state) }
  }
}
</script>

<style lang="scss" scoped>
.reactive_section {
  width: 100%;
  background-color: #2c3e50;
  color: whitesmoke;
  padding: 2rem;
  display: flex;
  justify-content: center;
  align-items: center;
  flex-direction: column;
}
.reactive__button {
  padding: 1rem 2rem;
  border: 1px solid #42b883;
  background-color: #35495e;
  color: whitesmoke;
  margin: 1rem 0 1rem 1rem;
  cursor: pointer;
}
.reactive__details {
  display: flex;
  flex-direction: column;
}
</style>