<script>
export default {
  computed: {
    userId() {
      return this.$route.params.userId;
    },
  },
};
</script>

<template>
  <section class="greeting">
    <h2 class="title">What's up! Who are you now?</h2>
    <div class="userList">
      <router-link to="/user:1">alvin</router-link>
      <router-link to="/user:2">jo</router-link>
      <router-link to="/user:3">gaby</router-link>
    </div>
  </section>
</template>
