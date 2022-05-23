<template>
  <div class="main__container">
    <MovieCard v-for="(item, index) in thumbs" :key="index" :movie="item" />
  </div>
</template>

<script>
import MovieCard from "./MovieCard.vue";
import axios from "axios";

export default {
  name: "AppMain",
  components: {
    MovieCard,
  },
  data: function () {
    return {
      thumbs: [],
    };
  },
  created() {
    axios
      .get("https://api.themoviedb.org/3/search/movie", {
        params: {
          api_key: "f8c2fc45385562d315d0006388000ea4",
          query: "la vita",
        },
      })
      .then((response) => {
        this.thumbs = response.data.results;
        console.log(this.thumbs);
      });
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
