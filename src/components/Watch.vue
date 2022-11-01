<template>
  <section class="watch__section">
    <div>
      <p>You have:
        <strong>{{shares}}</strong> shares and their value is
        <strong>{{ sharesValue }}$</strong>, because share price is
        <strong>{{sharePrice}}$</strong>.
      </p>
    </div>
  </section>
</template>

<script>
import { ref, computed } from "vue";

export default {
  name: "Watch",
  setup() {
    const shares = ref(15);
    const sharePrice = ref(20);
    const sharesValue = computed(() => shares.value * sharePrice.value);
    return { shares, sharePrice, sharesValue };
  }
};
</script>

<style lang="scss" scoped>
  .watch__section {
    width: 100%;
    display: flex;
    justify-content: center;
    align-items: center;
    div {
      max-width: 1366px;
      padding: 1rem 0;
    }
  }

</style>