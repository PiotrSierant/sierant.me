<script>
import Counting from "./components/Counting.vue";
import Events from "./components/Events.vue";
import Header from './components/Header.vue';
import List from './components/List.vue';
import Reactive from "./components/Reactive.vue";
import Watch from './components/Watch.vue';
import DynamicClass from './components/DynamicClass.vue';
import People from './components/PeopleList/People.vue';
export default {
    components: {
        Header,
        Counting,
        Events,
        List,
        Reactive,
        Watch,
        DynamicClass,
        People,
    }
}
</script>

<template>
    <Header />
    <Counting />
    <Events />
    <List />
    <Reactive />
    <Watch />
    <DynamicClass />
    <People />
</template>