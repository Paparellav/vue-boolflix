<template>
  <div class="main__container">
    <MovieCard v-for="(item, index) in movieArray" :key="index" :movie="item" />
  </div>
</template>

<script>
import MovieCard from "./MovieCard.vue";

export default {
  name: "AppMain",
  components: {
    MovieCard,
  },
  props: {
    movieArray: Array,
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
}
</style>
