<template>
  <div>
    <v-footer v-if="$vuetify.breakpoint.mdAndUp" color="rgba(92, 20, 39, .75)">
      <v-row justify="center" class="pt-4 pb-12">
        <span class="nav-item">
          <NuxtLink to="itinerary" class="link">Day-of Itinerary</NuxtLink>
        </span>
        <span class="nav-item">
          <NuxtLink to="our-story" class="link"> Our Story </NuxtLink>
        </span>
        <span class="nav-item">
          <NuxtLink to="faqs" class="link"> FAQs </NuxtLink>
        </span>
        <span class="nav-item">
          <NuxtLink to="/rsvp" class="link"> RSVP </NuxtLink>
        </span>
        <span class="nav-item">
          <NuxtLink to="/gallery" class="link"> Gallery </NuxtLink>
        </span>
        <span class="nav-item">
          <NuxtLink to="/wedding-party" class="link"> Wedding Party </NuxtLink>
        </span>
      </v-row>
    </v-footer>
    <v-col
      v-else
      justify="center"
      align="center"
      class="pt-6 pb-8 red-background-solid"
    >
      <div class="mb-3">
        <NuxtLink to="/rsvp" class="link"> RSVP </NuxtLink>
      </div>
      <div class="mb-3">
        <NuxtLink to="our-story" class="link"> Our Story </NuxtLink>
      </div>
      <div class="mb-3">
        <NuxtLink to="gallery" class="link"> Gallery </NuxtLink>
      </div>
      <div class="mb-3">
        <NuxtLink to="wedding-party" class="link"> Wedding Party </NuxtLink>
      </div>
      <div class="mb-3">
        <NuxtLink to="itinerary" class="link">Day-of Itinerary</NuxtLink>
      </div>
      <div class="mb-3">
        <NuxtLink to="faqs" class="link"> FAQs </NuxtLink>
      </div>
    </v-col>
  </div>
</template>

<style lang="scss" scoped>
.link {
  text-decoration: none;
}

.nav-item {
  text-decoration: none !important;
  padding: 0 25px;
  color: inherit;
  text-decoration: none;
}
</style>
