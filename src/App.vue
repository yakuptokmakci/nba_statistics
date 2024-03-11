<template>
  <div class="container">
    <div class="row">
      <v-app>
        <v-main>
          <Content />
          <ContentTable />
        </v-main>
      </v-app>
    </div>
    <div class="row">
      <Compare :players="filteredData" />
    </div>
  </div>
</template>

<script>
import axios from "axios";
import { onMounted } from "vue";
import ContentTable from "./components/ContentTable.vue";
import Compare from "./components/Compare.vue";

export default {
  setup() {
    onMounted(async () => {
      try {
        const response = await axios.get("src/assets/player_stats.json");
        const filteredData = response.data.map((item) => item.Rk);
        console.log(filteredData);
      } catch (error) {
        console.error("Error fetching data:", error);
      }
    });
  },
};
</script>
