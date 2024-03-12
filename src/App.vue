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
      <Compare :players="players" />
    </div>
  </div>
</template>

<script>
import axios from "axios";
import { onMounted, ref } from "vue";

export default {
  setup() {
    const players = ref([]);
    onMounted(async () => {
      try {
        const response = await axios.get("src/assets/player_stats.json");
        players.value = response.data;
        console.log(players.value);
      } catch (error) {
        console.error("Error fetching data:", error);
      }
    });
    return { players };
  },
};
</script>
