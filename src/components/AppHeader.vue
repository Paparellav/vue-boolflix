<template>
  <header class="header">
    <div class="header__title">
      <img src="../assets/img/logo.png" alt="logo-paparelflix" />
    </div>
    <div class="header__nav">
      <input
        type="text"
        placeholder="Cerca film, serie TV ecc."
        v-model="searchWord"
      />
      <button @click="$emit('parolaCercata', searchWord)">Cerca</button>
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
    width: 300px;

    img {
      width: 100%;
    }
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
      background-color: #db202c;
    }
  }
}
</style>
