<template>
  <section class="watch__section">
    <div>
      <p>You have:
        <strong>{{shares}}</strong> shares and their value is
        <strong>{{ sharesValue }}$</strong>, because share price is
        <strong>{{sharePrice}}$</strong>.
      </p>
      <button @click="changeNumberOfShares(1)">Buy one share</button>
      <button @click="changeNumberOfShares(5)">Buy five share</button>
      <button @click="changeNumberOfShares(-1)">Sell one share</button>
      <button @click="changeNumberOfShares(-5)">Sell five share</button>
    </div>
  </section>
</template>

<script>
import { ref, computed, watch } from "vue";

export default {
  name: "Watch",
  setup() {
    const shares = ref(15);
    const sharePrice = ref(20);
    const sharesValue = computed(() => shares.value * sharePrice.value);

    function changeNumberOfShares(number) {
      if(shares.value + number >=0) {
        shares.value += number;
      }
    }

    watch(shares, (shares, prevShares) => {
      console.log('shares: ', shares, 'prevShares: ', prevShares);
      shares > prevShares ? getPrice(1,5) : getPrice(-5,-1);
    })

    function getPrice(min, max) {
      const priceDiff = Math.floor(Math.random() * (max - min) + min)
      if(sharePrice.value + priceDiff >= 0) {
        sharePrice.value += priceDiff;
      }
    }

    return { shares, sharePrice, sharesValue, changeNumberOfShares };
  }
};
</script>

<style lang="scss" scoped>
  .watch__section {
    width: 100%;
    display: flex;
    justify-content: center;
    align-items: center;
    text-align: center;
    div {
      max-width: 1366px;
      padding: 1rem 0;
    }
  }
  button {
    margin-top: .5rem;
    padding: 1rem 2rem;
    border: 1px solid #42b883;
    background-color: #35495e;
    color: whitesmoke;
    cursor: pointer;
  }
</style>