<template>
  <section class="section_reactiveAndComputed">
    <h3>ComputedProperties and reactive</h3>
    <section class="boxes">
      <ComputedProperties />
      <section class="reactive_section">
        <button @click="makeOrder" class="reactive__button">Check func</button>
          <h3>Price: {{ price }}</h3>
          <h4>Quantity: {{ quantity }}</h4>
          <h4>Total price: {{ totalPrice }}</h4>
          <h4>Tax: {{ tax }}</h4>
      </section>
    </section>
  </section>
</template>

<script>
import { reactive, toRefs } from 'vue';
import ComputedProperties from "./ComputedProperties.vue";
export default {
  name: "Reactive",
  components: {
    ComputedProperties,
  },
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
.section_reactiveAndComputed {
  width: 100%;
  background-color: #2c3e50;
  color: whitesmoke;
  display: flex;
  flex-direction: column;
  padding: 2rem 0;
  text-align: center;
}
.boxes {
  display: flex;
  justify-content: space-evenly;
  flex-basis: 200px;
  flex-wrap: wrap;
  gap: 1rem;
  margin-top: 1rem;
}
.reactive_section {
  box-shadow: 1px 1px 5px rgba(0,0,0, .5);
  padding: 2rem;
}
.reactive__button {
  padding: 1rem 2rem;
  border: 1px solid #35495e;
  background-color: #42b883;
  color: whitesmoke;
  cursor: pointer;
}
</style>