<template>
  <div
    v-show="!hideCard"
    class="card"
    :style="{ border: '2px solid ' + spell.light }"
  >
    <button class="button" @click="hideCard = !hideCard">
      <img
        src="https://icon-library.com/images/cross-png-icon/cross-png-icon-23.jpg"
        alt="hide"
      />
    </button>

    <h2>{{ spell.name }}</h2>
    <h3>Incantation: "{{ spell.incantation }}"</h3>
    <p>{{ spell.effect }}</p>
  </div>
</template>

<script>
export default {
  name: "CardsH",
  props: ["spell"],
  data() {
    return {
      hideCard: false,
    };
  },
};
</script>

<style scoped>
.card {
  position: relative;
  background-color: white;
  width: 250px;
  border: 2px solid;
  border-radius: 8px;
  font-weight: bold;
  padding: 10px;
  font-size: 0.9rem;
  border: 2px solid black;
}
button {
  position: absolute;
  right: 0;
  background: transparent;
  border: 0;
  cursor: pointer;
}
button img {
  width: 20px;
  border: 0;
}
h2 {
  margin: 2px 2px 20px 2px;
}
h3 {
  margin: 3px;
  text-align: left;
  font-weight: bold;
  font-family: "Dosis", sans-serif;
}
p {
  margin-bottom: 0px;
  margin-top: 6px;
  color: #a7a7a7;
  text-align: left;
  font-weight: lighter;
  font-size: 0.8rem;
}
@media (min-width: 767px) {
  .card {
    width: 350px;
  }
}
</style>
