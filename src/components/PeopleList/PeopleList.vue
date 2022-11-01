<template>
  <div class="person__wrap">
    <Person
      v-for="(item, index) in items"
      :key="item.id"
      :index="index"
      :item="item"
    />
  </div>
</template>

<script>
import Person from "./Person.vue";
export default {
  name: "PeopleList",
  components: {
    Person,
  },
  props: {
    items: {
      type: Array,
      default: () => [
        {
          id:1,
          firstName: 'Pjoter',
          lastName: 'Me',
          age: 26,
          party: null,
        },
        {
          id:2,
          firstName: 'Pjoter2',
          lastName: 'Me2',
          age: 22,
          party: 'Siemka',
        }
      ]
    }
  },
};
</script>

<style lang="scss" scoped>
.person__wrap {
  width: 100%;
  max-width: 1366px;
  display: flex;
  flex-wrap: wrap;
  padding: 2rem;
}
</style>