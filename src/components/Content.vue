<template>
  <h2>NBA Statistics</h2>
  <v-card
    variant="outlined"
    image="https://cdn.vuetifyjs.com/images/cards/docks.jpg"
  >
    <template #title>{{ title }}</template>
    <template #text>{{ main_idea + how_to_use }}</template>
  </v-card>
</template>

<script setup>
const title = "Scope Of the Project";
const main_idea =
  "The central objective of this project is to compare the statistics of two players  As you may be aware, the NBA has a committee primarily focused on statistics. Therefore, our application serves as the optimal solution to fulfill this interest. Our app can furnish comprehensive statistics for over 700 players in the latest NBA season";
const how_to_use =
  "The user selects the desired two players from the statistics table and through an advanced algorithm, compares them to see which player had a better season.";
</script>
