<template>
  <v-timeline
    align-top
    class="mx-md-4 my-md-8 mr-2"
    color="rgba(0,0,0,0)"
    :dense="$vuetify.breakpoint.mdAndDown"
  >
    <v-timeline-item
      v-for="item in itinerary"
      :key="item.index"
      color="white"
      fill-dot
      small
      class="my-md-n10"
    >
      <v-card color="rgba(92, 20, 39, 0.75)">
        <v-card-title>
          {{ item.time }}
        </v-card-title>
        <v-card-text>
          {{ item.content }}
          <div v-if="item.add" class="text-caption" v-html="item.add" />
        </v-card-text>
      </v-card>
    </v-timeline-item>
  </v-timeline>
</template>

<script>
export default {
  name: 'ItineraryComponent',
  props: ['itinerary'],
}
</script>
