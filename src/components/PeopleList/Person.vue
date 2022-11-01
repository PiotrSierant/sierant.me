<template>
  <div class="person">
    <p>Candidate: <strong>{{ index + 1 }}</strong></p>
    <p>Name: <strong>{{ item.firstName }} {{ item.lastName }}</strong></p>
    <p>Age: <strong>{{ ageWithYears }}</strong></p>
    <p v-if="item.party">Party: <strong>{{ item.party }}</strong></p>
    <p v-if="item.opinionPool">
      Opinion pool: <strong><progress max="100" :value="item.opinionPool"></progress> {{ item.opinionPool }}%</strong></p>
  </div>
</template>

<script>
import { computed } from "vue";

export default {
  name: "Person",
  props: {
    item: {
      type: Object,
      default: () => {},
    },
    index: {
      type: Number,
      default: 0,
    },
  },
  setup(props) {
    const ageWithYears = computed(() => `${props.item.age} years`);
    return { ageWithYears };
  },
};
</script>

<style lang="scss" scoped>
.person {
  border: 1px solid whitesmoke;
  display: flex;
  flex-direction: column;
  flex-shrink: 1;
  flex-basis: 310px;
  padding: .5rem;
  box-shadow: 3px 3px 5px rgba(0,0,0, .5);
  p {
    color: whitesmoke;
    strong {
      color: #42b883;
    }
  }
}
</style>