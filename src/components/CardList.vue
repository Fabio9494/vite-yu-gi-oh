<script>
import { store } from '../store.js';
import Cards from '../components/Cards.vue';
export default {
    components: {
        Cards
    },
    data() {
        return {
            store,
        }
    },
}
</script>

<template lang="">
    <div class="container">
        <div class="cards-container">
            <Cards v-for="card, index in store.cardsList" :key="index" :card="card"/>
        </div>
    </div>
</template>

<style lang="scss" scoped>
.container {
    background-color: rgb(165, 122, 42);
    display: flex;
    justify-content: center;
    align-items: center;
    flex-direction: column;
    padding: 20px 0;
}

.cards-container {
    width: 90%;
    background-color: white;
    display: flex;
    flex-wrap: wrap;
    justify-content: center;
    padding: 20px;
}

.margin-20 {
    margin: 20px;
}
</style>