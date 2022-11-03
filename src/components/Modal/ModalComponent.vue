<template>
    <section class="modalSection">
        <div class="container">
            <button class="button" 
                @click="handleClick" 
                :class="[!isActive ? 'open' : 'hide']">
                Open Modal
            </button>
            <section v-if="isActive" @click="handleClick" class="modal">
                hello
            </section>
        </div>
    </section>
</template>
<script>
import { ref } from 'vue';
export default {
    name: "ModalComponent",
    setup() {
        const isActive = ref(false);
        function handleClick () {
            this.isActive = !this.isActive;
        }
        return { isActive, handleClick }
    }
}
</script>
<style lang="scss" scoped>
    .modalSection {
        width: 100%;
        background-color: rgb(90, 90, 90);
        display: flex;
        justify-content: center;
        align-items: center;
    }    
    .container {
        width: 100%;
        max-width: 1366px;
        display: flex;
        justify-content: center;
        align-items: center;
    }
    .button {
        padding: 1rem 2rem;
        border: none;
        background-color: #35495e;
        cursor: pointer;
        color: whitesmoke;
    }
    .open {
        display: flex;
    }
    .hide {
        display: none;
    }
    .modal {
        width: 100%;
        border: 1px solid darkgreen;
        background-color: aliceblue;
    }
</style>