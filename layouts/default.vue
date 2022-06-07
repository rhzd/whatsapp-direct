<template>
  <v-app>
    <v-main>
      <v-container>
        <Nuxt />
      </v-container>
    </v-main>
  </v-app>
</template>

<script>
export default {
  data() {
    return {};
  },
};
</script>

<style>
html {
  min-height: calc(100% + env(safe-area-inset-top));
  margin: env(safe-area-inset-top) env(safe-area-inset-right) env(safe-area-inset-bottom) env(safe-area-inset-left);
}
html, body {
  overflow-x: hidden;
}
body {
  position: relative;
}
</style>
