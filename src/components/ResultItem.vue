<template>
  <div class="resultStripe">
    <div>
      <img class="teaserImage" v-bind:src="teaserImage.src" />
    </div>
    <div class="itemWrapper shadow-sm">
      <a href="link">
        <h1 class="itemTitle">{{ title }}</h1>
      </a>
      <div class="dateInfo">{{ date }}</div>
      <p class="item-description">{{ description }}</p>
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
    title: {
      type: String,
      required: true,
    },
    teaserImage: {
      type: String,
      required: true,
    },
    description: {
      type: String,
      required: true,
    },
    date: {
      type: String,
      required: true,
    },
  },
  // actions
  methods: {},
};
</script>

<style>
.resultStripe {
    display:flex;
    align-items: center;
}
.itemWrapper {
  background: #f4f4f4;
  padding: 10px;
  margin-left:10px;
  margin-bottom: 10px;
  border-radius: 2px;
}
.itemWrapper a {
  text-decoration: none;
}

.teaserImage {
  height: 100px;
}
.itemTitle {
  color: #0089de;
  font-size: 16px;
  font-weight: bold;
  color: #6f6f6f;
}

.dateInfo {
  background: #cacaca;
  width: 100px;
  display: flex;
  justify-content: center;
  align-items: center;
  border-radius: 2px;
}

.item-description {
  color: #3e3e3e;
}
</style>