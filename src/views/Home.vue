<template>
  <div class="flex flex-col p-8">
  </div>
</template>

<script setup>
// import { computed } from "vue";
import { onMounted, ref } from "vue";
// import store from "../store/index.js";
import axiosClient from "../axiosClinet.js";

const ingredients = ref([]);

onMounted(async () => {
  const response = await axiosClient.get("/list.php?i=list");
  ingredients.value = response.data;
});
</script>
