<template>
  <v-row justify="center" align="center" class="mb-12">
    <v-col cols="12">
      <Home />
    </v-col>
    <v-btn x-large to="/rsvp" color="rgba(92, 20, 39, 1)"> RSVP </v-btn>
  </v-row>
</template>

<script>
import Home from '@/components/Home.vue'

export default {
  name: 'IndexPage',
  components: {
    Home,
  },
}
</script>
