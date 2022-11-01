<template>
<!--  <section class="dynamicClass" @click="handleClick" :class="{ active: isActive, 'text-danger': hasError }">-->
<!--    <p>Click me and change my style!</p>-->
<!--  </section>-->
<!--  <section class="dynamicClass" @click="handleClick"  :class="[{active: isActive},{'text-danger': hasError}]">-->
<!--    <p>Click me and change my style!</p>-->
<!--  </section>-->
  <section class="dynamicClass" @click="handleClick"  :class="[isActive ? 'active' : 'text-danger']">
    <p>Click me and change my style!</p>
  </section>
</template>

<script>
import { ref } from 'vue';
export default {

  name: "DynamicClass",
  setup() {
    const isActive = ref(true);
    const hasError = ref(false);
    const count = ref(0);
    function handleClick() {
      this.isActive = !this.isActive;
      this.count++
      if(this.count > 4) {
        this.hasError = true;
      }
    }
    return { isActive, hasError, count, handleClick }
  }
};
</script>

<style lang="scss" scoped>
  .dynamicClass {
    background-color: #2c3e50;
    min-height: 20vh;
    width: 100%;
  }
  .active {
    background-color: #42b883;
  }
  .text-danger {
    border: 2px solid #42b883;
    background-color: #cb1e1e;
    color: whitesmoke;
    padding: 3rem;
  }
</style>