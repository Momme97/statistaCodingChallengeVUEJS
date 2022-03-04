<script setup>
import SearchResults  from "./components/SearchResults.vue";
</script>

<template>
  <div class="container mt-5">
    <img class="statistaLogo" src="./assets/Statista-Logo.png" />
    <input  class="inputStyle mt-2" placeholder="Statista rocks !" key="searchBox" type="text" v-on:change="startSearch($event)" />
    <SearchResults :searchList="this.searchItems"></SearchResults>
  </div>
</template>

<script>
import axios from "axios";

export default {
  // state
  data() {
    return {
      searchItems: [],
    };
  },
  // actions
  methods: {
    async startSearch(event) {
      /***************************
        If search string match company name set state with results
        ***************************/
      if (event.target.value === "Statista") {
        const searchResp = await axios.get(
          "https://cdn.statcdn.com/static/application/search_results.json"
        );
        this.searchItems = searchResp.data.items;
        console.log(this.searchItems);
      }
    },
  },
};
</script>

<style>
.inputStyle {
  width:100%;
}
.statistaLogo {
  height: 50px;
}
</style>
