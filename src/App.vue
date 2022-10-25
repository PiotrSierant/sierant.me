<script>
import Counting from "./components/Counting.vue";
import Events from "./components/Events.vue";
import Header from './components/Header.vue';
export default {
    components: {
        Header,
        Counting,
        Events,
    }
}
</script>

<template>
    <Header />
    <Counting />
    <Events />
</template>