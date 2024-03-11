<template>
  <div class="container">
    <v-btn color="black" @click="handleClick" v-if="isCompare"
      >Compare The Players</v-btn
    >
    <div class="row" v-if="!isCompare">
      <div class="col">
        <button
          class="btn btn-secondary btn-lg dropdown-toggle"
          type="button"
          data-bs-toggle="dropdown"
          aria-expanded="false"
        >
          Slecet Player 1
        </button>
      </div>
      <div class="col">
        <button
          class="btn btn-secondary btn-lg dropdown-toggle"
          type="button"
          data-bs-toggle="dropdown"
          aria-expanded="false"
        >
          Slecet Player 2
        </button>
      </div>
    </div>
  </div>
</template>

<script setup>
import { ref } from "vue";

const props = defineProps(["players"]);

const isCompare = ref(true);

const handleClick = () => {
  isCompare.value = !isCompare.value;
  console.log(isCompare.value);
};
</script>
