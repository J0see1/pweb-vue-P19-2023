<script setup>
import { ref, onMounted, watch } from "vue";

const name = ref("");

watch(name, (newVal) => {
  localStorage.setItem("name", newVal);
});

onMounted(() => {
  name.value = localStorage.getItem("name") || "";
});
</script>

<template>
  <section class="greeting">
    <h2 class="title">
      What's up,
      <input type="text" id="name" placeholder="Name here" v-model="name" />
    </h2>
    <h3>How's your week? care to plan the next one?</h3>
  </section>
</template>
