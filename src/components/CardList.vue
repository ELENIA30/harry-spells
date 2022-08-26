<template>
  <div class="wrapper">
    <h4>Your Spells</h4>
    <div class="cardswrapper">
      <Cards
        v-for="spell in spellList"
        :key="spell.id"
        :spell="spell"
      />
    </div>
  </div>
</template>

<script>
import Cards from "./Cards.vue";

export default {
  name: "CardList",
  components: { Cards },
  props: ["spellList"],
};
</script>

<style scoped>
.wrapper {
  display: flex;
  flex-direction: column;
  flex-wrap: wrap;
  background-color: #f0f0f0;
  align-items: center;
}
.cardswrapper {
  display: flex;
  flex-wrap: wrap;
  justify-content: center;
  gap: 10px;
}
</style>
