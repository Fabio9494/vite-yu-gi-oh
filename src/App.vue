<script>
import AppHeader from './components/AppHeader.vue';
import CardList from './components/CardList.vue';
import Search from './components/Search.vue';
import axios from 'axios';


import { store } from './store.js'

export default {
  components: {
    AppHeader,
    CardList,
    Search
  },
  data() {
    return {
      store
    }
  },

  created() {
    this.getCardList()

  },

  methods: {
    getCardList() {
      let api = store.endpoint

      if (store.type !== '') {
        api += `&archetype=${store.type}`
      }

      axios.get(api).then((response) => {
        store.cardsList = response.data.data;
      })
    },
  },
}
</script>

<template lang="">
    <div>
        <AppHeader/>
        <Search @filter_cards="getCardList"/>
        <CardList/>
    </div>
</template>

<style lang="scss"></style>