<template>
  <div>
    <div class="small-title">Thank you for your RSVP!</div>
    <div class="">
      We've received information for the following guests:
      <div v-for="attendee in attendee" :key="attendee.name">
        <div v-if="attendee.name !== ''">
          {{ attendee.name }}
        </div>
      </div>
    </div>
    <div class="py-8">
      <div class="pb-6">We look forward to seeing you on August 13th!</div>
      <v-row class="pb-8">
        <v-col cols="12" md="6">
          <div>Cermony Information:</div>
          <div>2:45PM - August 13th, 2022</div>
          <div>
            <a
              href="https://goo.gl/maps/8dSxrNsw6xDeF6qj7"
              target="_blank"
              rel="noreferrer"
              >Raven Picnic Site in North Glenmore Park</a
            >
          </div>
        </v-col>
        <v-col cols="12" md="6">
          <div>Reception Information:</div>
          <div>6:00PM - August 13th, 2022</div>
          <div>
            <a
              href="https://goo.gl/maps/3LVz3ydgCZZuJiYF8"
              target="_blank"
              rel="noreferrer"
              >Heritage Park</a
            >
          </div>
        </v-col>
      </v-row>
      <v-btn color="rgba(92, 20, 39, 1)" :nuxt="true" to="/itinerary"
        >Day-of Itinerary</v-btn
      >
    </div>
  </div>
</template>

<script>
export default {
  name: 'RsvpSuccess',
  props: ['attendee'],
}
</script>
