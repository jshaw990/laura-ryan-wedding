<template>
  <v-app dark>
    <div class="bg-image">
      <h1
        v-if="error.statusCode === 404"
        class="small-title red-background-trans"
      >
        {{ pageNotFound }}
      </h1>
      <h1 v-else class="small-title red-background-trans">
        {{ otherError }}
      </h1>
    </div>
  </v-app>
</template>

<script>
export default {
  name: 'EmptyLayout',
  layout: 'empty',
  props: {
    error: {
      type: Object,
      default: null,
    },
  },
  data() {
    return {
      pageNotFound: '404 Not Found',
      otherError: 'An error occurred',
    }
  },
  head() {
    const title =
      this.error.statusCode === 404 ? this.pageNotFound : this.otherError
    return {
      title,
    }
  },
}
</script>

<style lang="scss" scoped>
.bg-image {
  background-image: url('../static/background-other.jpg');
  background-position: top-center;
  background-repeat: no-repeat;
  background-size: cover;
  width: 100%;
  height: 100vh;
  text-align: center;
  h1 {
    width: fit-content;
    margin: 50px auto;
    padding: 3rem;
  }
}
</style>
