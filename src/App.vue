<template>
    <v-app>
    <v-main class="desk">
      <router-view />
    </v-main>
  </v-app>
</template>

<script>
export default {
  name: 'App',

  data: () => ({
    //
  }),
};
</script>

<style>
  .desk {
    background: #004D98;
  }
</style>