<script setup>
import { RouterLink, RouterView } from "vue-router";
</script>
<template>
  <section class="navbar">
    <div class="logo">
      <a href="/"> Portal </a>
    </div>
    <div class="menu">
      <ul>
        <li><RouterLink to="/">home</RouterLink></li>
        <li><RouterLink to="/about">about</RouterLink></li>
        <li><RouterLink to="404">content</RouterLink></li>
      </ul>
    </div>
  </section>
</template>
