<template>
  <v-app dark>
    <StaticHeader />
    <v-main class="bg-image">
      <Nuxt />
    </v-main>
    <StaticFooter />
  </v-app>
</template>

<script>
export default {
  name: 'DefaultLayout',
}
</script>

<style lang="scss" scoped>
.bg-image {
  background-image: url('../static/background-other.jpg');
  background-position: top-center;
  background-repeat: no-repeat;
  background-size: cover;
  width: 100%;
}
</style>
