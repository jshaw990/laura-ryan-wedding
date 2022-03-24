<template>
  <v-col cols="12" md="8" class="mx-auto page">
    <div class="m-8 small-title background-hue">Day-of Itinerary</div>
    <v-card color="rgba(0,0,0,0)">
      <ItineraryComponent :itinerary="itinerary" />
    </v-card>
  </v-col>
</template>

<script>
import { reactive, toRefs } from '@vue/composition-api'

import itinerary from '@/static/itinerary.json'

import ItineraryComponent from '~/components/ItineraryComponent.vue'

export default {
  name: 'Itinerary',
  components: {
    ItineraryComponent,
  },

  setup() {
    const state = reactive({
      itinerary,
    })

    return {
      ...toRefs(state),
    }
  },
}
</script>
