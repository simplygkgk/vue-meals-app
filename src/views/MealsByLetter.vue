<template>
  <div class="flex gap-2 mt-2 justify-center">
    <router-link
      :to="{ name: 'byLetter', params: { letter } }"
      :key="letter"
      v-for="letter of letters"
    >
      {{ letter }}
    </router-link>
  </div>
  <Meals :meals="meals"></Meals>
</template>

<script setup>
import { useRoute } from "vue-router";
import store from "../store";
import { computed, onMounted, watch } from "vue";
import Meals from "../components/Meals.vue";

const letters = "ABCDEFGHIJKLMONPQRTUVWXYZ".split("");
const route = useRoute();
const meals = computed(() => store.state.mealsByLetter);

watch(route, () => {
  store.dispatch("searchMealsByLetter", route.params.letter);
});

onMounted(() => {
  store.dispatch("searchMealsByLetter", route.params.letter);
});
</script>
