<template>
  <v-col cols="12" md="10" class="page mx-auto">
    <RsvpForm />
  </v-col>
</template>

<script>
import FaqComponent from '~/components/FaqComponent.vue'

export default {
  components: { FaqComponent },
  name: 'RSVP',
}
</script>
