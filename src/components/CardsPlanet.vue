<template>
  <div>
    <h1 class="name"></h1>
    <div>
      <!-- TODO: Надо выводить счетчик общей популяции на всех планетах -->
      <TheCardsItem
        v-for="info in fullData"
        :key="info.name"
        :fullData="info"
      />
    </div>
  </div>
</template>

<script>
import TheCardsItem from "./TheCardsItem";
import API_STARWARS_URL from "@/constant.js";

export default {
  components: { TheCardsItem, API_STARWARS_URL },
  name: "CardsPlanet",
  data() {
    return {
      /** пробрасывать пропсами */
      fullData: [],
      namePlanetinfo: [],
      climatePlanetInfo: [],
      population: [],
    };
  },

  async beforeCreate() {
    /** TODO: перенести в отдельный файл, адрес задавать константой */
    // const response = await fetch(API_STARWARS_URL);// почему то не видит константу 
    const response = await fetch("https://swapi.dev/api/planets/");
    const respJson = await response.json();

    this.fullData = respJson.results.map((e) => ({
      name: e.name,
      cli: e.climate,
      pop: e.population,
    }));
  },
};
</script>