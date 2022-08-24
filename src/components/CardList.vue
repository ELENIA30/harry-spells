<template>
  <div class="wrapper">
    <h4>Your Spells</h4>
    <div class="cardswrapper">
      <CardsH
        v-for="spell in spellList"
        :key="spell.id"
        :spell="spell"
      />
    </div>
  </div>
</template>

<script>
import CardsH from "./CardsH.vue";

export default {
  name: "CardList",
  components: { CardsH },
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
