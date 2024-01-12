<script>
import axios from 'axios';
import { store } from '../store.js';
export default {
    name: 'SelectType',
    data() {
        return {
            store,
            typeCards: []
        }
    },
    created() {
        this.getArchetypesList()
    },
    methods: {
        getArchetypesList() {
            axios.get(store.apiArchetype).then((response) => {
                this.typeCards = response.data
            })
        }
    },
}
</script>

<template lang="">
    <div>
        <select @click="$emit('filter_cards')" name="type" id="type" v-model="store.type" >
            <option value="">Seleziona tipo</option>
            <option v-for="(type, index) in typeCards" :key="index" :value="type.archetype_name" >
                {{type.archetype_name}}
            </option>
        </select>
    </div>
</template>

<style lang="scss" scoped>
select {
    width: 150px;
    padding: 5px;
}
</style>