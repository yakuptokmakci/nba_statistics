<template>
  <v-data-table
    :items="items"
    loading-text="Loading... Please wait"
    height="300"
    item-value="name"
    theme="dark"
  ></v-data-table>
</template>

<script setup>
import axios from "axios";
import { ref, onMounted } from "vue";

const items = ref([]);

onMounted(async () => {
  try {
    const response = await axios.get("src/assets/player_stats.json");
    items.value = response.data;
  } catch (error) {
    console.error("Error fetching data:", error);
  }
});
</script>

<style>
.v-data-table tbody tr:hover {
  cursor: pointer;
}
</style>
