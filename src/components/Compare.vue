<template>
  <div class="container">
    <v-btn color="black" @click="handleClick" v-if="isCompare"
      >Compare The Players</v-btn
    >
    <div v-else>
      <div class="row">
        <div class="col">
          <select v-model="selectedPlayer1" class="form-select bg-secondary">
            <option value="" disabled>Select Player 1</option>
            <option
              v-for="player in players"
              :key="player.Rk"
              :value="player.Rk"
            >
              {{ player.Rk }}
            </option>
          </select>
        </div>
        <div class="col">
          <select v-model="selectedPlayer2" class="form-select bg-secondary">
            <option value="" disabled>Select Player 2</option>
            <option
              v-for="player in players"
              :key="player.Rk"
              :value="player.Rk"
            >
              {{ player.Rk }}
            </option>
          </select>
        </div>
      </div>
      <div class="row">
        <div class="col">
          <button type="button" class="btn btn-success" @click="handleCompare">
            Compare
          </button>
          <button
            type="button"
            class="btn btn-danger ms-1"
            @click="RemoveCompare"
          >
            Discard
          </button>
        </div>
      </div>
      <div class="row" v-if="compare_cards"><h2>mal</h2></div>
    </div>
  </div>
</template>

<script setup>
import { ref } from "vue";

const props = defineProps(["players"]);

const isCompare = ref(true);
const compare_cards = ref(false);
const selectedPlayer1 = ref("");
const selectedPlayer2 = ref("");

const handleClick = () => {
  isCompare.value = !isCompare.value;
};

const handleCompare = () => {
  compare_cards.value = true;
};

const RemoveCompare = () => {
  compare_cards.value = false;
};
</script>
