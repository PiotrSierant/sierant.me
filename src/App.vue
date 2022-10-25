<script>
import Counting from "./components/Counting.vue";
import Events from "./components/Events.vue";
import Header from './components/Header.vue';
import List from './components/List.vue';
export default {
    components: {
        Header,
        Counting,
        Events,
        List,
    }
}
</script>

<template>
    <Header />
    <Counting />
    <Events />
    <List />
</template>