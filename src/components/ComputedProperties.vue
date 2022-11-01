<template>
  <section class="computedProperties_section">
    <button @click="makeOrder" class="computedProperties__button">Check func</button>
      <h3>Price: {{ price }}</h3>
      <h4>Quantity: {{ quantity }}</h4>
      <h4>Total price: {{ totalPrice }}</h4>
      <h4>Tax: {{ tax }}</h4>
  </section>
</template>

<script>
import { ref, computed } from "vue";

export default {
  name: "ComputedProperties",
  setup() {
    const quantity = ref(0);
    const price = ref(100);
    const totalPrice = computed(() => quantity.value * price.value);
    const tax = computed(() => totalPrice.value * 0.23);
    
    function makeOrder() {
      quantity.value++
    }
    
    return { quantity, price, totalPrice, tax, makeOrder}
  }
};
</script>

<style scoped>
.computedProperties_section {
  box-shadow: 1px 1px 5px rgba(0,0,0, .5);
  padding: 2rem;
}
.computedProperties__button {
  padding: 1rem 2rem;
  border: 1px solid #35495e;
  background-color: #42b883;
  color: whitesmoke;
  cursor: pointer;
}
</style>