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
      <div class="row" v-if="compare_cards">
        <v-card class="mx-auto bg-secondary" max-width="344">
          <v-img
            height="200px"
            src="https://encrypted-tbn0.gstatic.com/images?q=tbn:ANd9GcR3rCVTROB4ZmRelcdj3kcnYoGvnNwesVbjAQ&usqp=CAU"
            cover
          ></v-img>

          <v-card-title> According To Our Algorithm </v-card-title>

          <v-card-subtitle> The statistical Winner is </v-card-subtitle>

          <v-card-actions>
            <v-btn color="orange-lighten-3" variant="text"> Explore </v-btn>

            <v-spacer></v-spacer>

            <v-btn
              :icon="show ? 'mdi-chevron-up' : 'mdi-chevron-down'"
              @click="show = !show"
            ></v-btn>
          </v-card-actions>

          <v-expand-transition>
            <div v-show="show">
              <v-divider></v-divider>

              <v-card-text>
                I'm a thing. But, like most politicians, he promised more than
                he could deliver. You won't have time for sleeping, soldier, not
                with all the bed making you'll be doing. Then we'll go with that
                data file! Hey, you add a one and two zeros to that or we walk!
                You're going to do his laundry? I've got to find a way to
                escape.
              </v-card-text>
            </div>
          </v-expand-transition>
        </v-card>
      </div>
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
const show = ref(false);

const handleClick = () => {
  isCompare.value = !isCompare.value;
};

const handleCompare = () => {
  compare_cards.value = true;
};

const RemoveCompare = () => {
  compare_cards.value = false;
  isCompare.value = true;
};
</script>
