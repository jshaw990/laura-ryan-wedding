<template>
  <div class="bg-page">
    <v-col cols="12" md="8" class="mx-auto page">
      <div v-for="image in images" :key="image.index">
        <v-img :src="image.url" contain class="mx-md-3 bg-white my-6" />
      </div>
    </v-col>
  </div>
</template>

<script>
import { reactive, toRefs } from '@vue/composition-api'

import images from '@/static/gallery.json'

export default {
  name: 'Gallery',
  setup() {
    const state = reactive({
      images,
    })

    return {
      ...toRefs(state),
    }
  },
}
</script>

<style lang="scss" scoped>
.bg-page {
  width: 100%;
  margin: 0;
  padding: 0;
  margin-top: -128px;
  padding-top: 128px;
  background-image: url('@/static/background-other.jpg');
  background-position: top-center;
  background-repeat: repeat-y;
  background-size: contain;
}
</style>
