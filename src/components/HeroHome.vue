<template>
  <div class="heroHome">
    <div class="title">
      <h1>Wizard, We Help You Find Your Spell</h1>
      <h3>Find spells in anywhere, just tapping your smartphone</h3>
    </div>
    <div class="imghero">
      <img class="img" src="../assets/harry-hero.jpg" />
    </div>
      <form class="search">
        <input type="text" v-model="input" placeholder="Spell name..."/>
        <button @click.prevent="getSpells" class="button">Search</button>
      </form>
  </div>
</template>

<script>
  import axios from "axios";

  export default {
    name:"HeroHome",
    props:["onSubmit"],
    data() {
      return {
        input: "",
      }
    },
    methods: {
      getSpells() {
        axios.get('https://wizard-world-api.herokuapp.com/Spells')
        .then((spells) => {
          this.$emit("spellsData", spells.data.filter(item => item.effect.toLowerCase().includes(this.input.toLowerCase())))
        })
      },
    },
  }
</script>

<style scoped>
h1{
  color: #000000;
}
h3{
  color:#8D8D8D;
  font-family: 'Dosis', sans-serif;
}
img{
  height: 268px;
  width: 268px;
}
.heroHome{
  margin-bottom: 60px;
}
.search{
  margin: 6px;
}
.search input{
  padding: 6px 6px 3px 12px;
  outline: none;
  border: 1px solid black;
  border-right: 0;
  border-start-start-radius: 8px;
  border-end-start-radius: 8px;
}
.button{
  padding: 5px;
  border: 0;
  background-color: #000000;
  color: white;
  border-left: 0;
  border-top-right-radius: 8px;
  border-end-end-radius: 8px;
  font-weight: bold;
  cursor: pointer;
  font-family: 'Dosis', sans-serif;
}
::placeholder{
   font-family: 'Dosis', sans-serif;
}

</style>