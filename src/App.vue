<script>
import Counting from "./components/Counting.vue";
import Events from "./components/Events.vue";
import Header from './components/Header.vue';
import List from './components/List.vue';
import Reactive from "./components/Reactive.vue";
import ComputedProperties from "./components/ComputedProperties.vue";
export default {
    components: {
        Header,
        Counting,
        Events,
        List,
        Reactive,
        ComputedProperties,
    }
}
</script>

<template>
    <Header />
    <Counting />
    <Events />
    <List />
    <Reactive />
    <ComputedProperties />
</template>