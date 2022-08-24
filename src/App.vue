<template>
  <NavBar scrollTop="scrollTop" />
  <HeroHome @spellsData="setSpellList" />
  <CardList v-if="spellList.length >= 1" :spellList="spellList" />
  <h3 v-else>{{noSpellsFound ? "No spells found" : "Search for a spell!"}}</h3>
  <button class="scrollTop">
    <a href="#scrollTop">
      <img src="https://upload.wikimedia.org/wikipedia/commons/6/61/Black_Up_Arrow.png" alt="top">
    </a>
  </button>
</template>

<script>
import NavBar from "./components/NavBar.vue";
import HeroHome from "./components/HeroHome.vue";
import CardList from "./components/CardList.vue";

export default {
  name: "App",
  components: {
    NavBar,
    HeroHome,
    CardList,
  },
  data() {
    return {
      spellList: [],
      noSpellsFound: false
    };
  },
  methods: {
    setSpellList(payload) {
      if (payload.length === 0) this.noSpellsFound = true;
      this.spellList = payload;
    },
  },
};
</script>

<style>
@import url('https://fonts.googleapis.com/css2?family=Dosis:wght@300&family=Lobster&family=Yusei+Magic&display=swap');
html {
  scroll-behavior: smooth;
}

#app {
  font-family: "Yusei Magic", sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
  scroll-behavior: smooth;
}
h3{
  font-family: 'Dosis', sans-serif;
}

.scrollTop {
  border: 0;
  position: fixed;
  bottom: 30px;
  right: 30px;
  background: transparent;
}

.scrollTop img {
  width: 30px;
  height: 40px;
}
</style>
