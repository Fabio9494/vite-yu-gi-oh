<script>
import { store } from '../store.js';
export default {
    name: 'SelectType',
    data() {
        return {
            store,
            typeCards: [
                'Alien',
                'Noble Knight',
                'Melodious',
                'Archfiend'
            ]
        }
    },
    methods: {

    },
}
</script>

<template lang="">
    <div>
        <select @click="$emit('filter_cards')" name="type" id="type" v-model="store.type" >
            <option value="">Seleziona tipo</option>
            <option v-for="(type, index) in typeCards" :key="index" :value="type" >
                {{type}}
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