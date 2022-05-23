<template>
  <header class="header">
    <h1 class="header__title">Boolflix</h1>
    <div class="header__nav">
      <input
        type="text"
        placeholder="Cerca film, serie TV ecc."
        v-model="searchWord"
      />
      <button @click="searchFunction">Cerca</button>
    </div>
  </header>
</template>

<script>
export default {
  name: "AppHeader",
  data: function () {
    return {
      searchWord: "",
    };
  },
  methods: {
    searchFunction() {
      console.log("Sto cercando");
    },
  },
};
</script>

<style lang="scss" scoped>
.header {
  width: 100%;
  height: 100px;
  display: flex;
  justify-content: space-evenly;
  align-items: center;
  background-color: #141414;

  &__title {
    font-size: 2.6rem;
    text-transform: uppercase;
    color: #b82b28;
  }

  &__nav {
    input {
      width: 250px;
      padding: 0.5rem 1rem;
      border-radius: 10px;
      border: none;
    }

    button {
      cursor: pointer;
      padding: 0.5rem 2rem;
      margin: 0 1rem;
      border-radius: 10px;
      border: none;
      color: white;
      background-color: #b82b28;
    }
  }
}
</style>
