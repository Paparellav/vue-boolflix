<template>
  <div class="main__container">
    <h2>Films</h2>
    <AppCard v-for="(item, index) in movieArray" :key="index" :cardObj="item" />
    <h2>Series</h2>
    <AppCard
      v-for="(item, index) in tvArray"
      :key="'A' + index"
      :cardObj="item"
    />
  </div>
</template>

<script>
import AppCard from "./AppCard.vue";

export default {
  name: "AppMain",
  components: {
    AppCard,
  },
  props: {
    movieArray: Array,
    tvArray: Array,
  },
};
</script>

<style lang="scss" scoped>
.main__container {
  width: 80%;
  margin: 2rem auto;
  display: flex;
  flex-wrap: wrap;
  color: white;

  h2 {
    width: 100%;
    margin: 2rem 0;
    margin-left: 1rem;
  }
}
</style>
