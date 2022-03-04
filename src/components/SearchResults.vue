<script setup>
import ResultItem from './ResultItem.vue';
</script>

<template>
  <div>
      <p>Anzahl Ergebnisse: {{searchList.length}}</p>
    <div v-if="searchList.length > 0">
        <div v-for="searchResult in searchList" :key="searchResult.identifier">
            <ResultItem :title="searchResult.title" :teaserImage="searchResult.teaser_image_urls[1]" :description="searchResult.description" :date="searchResult.date" ></ResultItem>
        </div>
    </div>
  </div>
</template>

<script>
export default {
  // state
  data() {
    return {};
  },
  props: {
    searchList: {
      type: Array,
      required: true,
    },
  },
  // actions
  methods: {},
};
</script>