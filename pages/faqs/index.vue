<template>
  <v-col cols="12" md="10" class="mx-auto page">
    <div class="m-8 px-2 small-title background-hue">
      Frequently Asked Questions
    </div>
    <v-expansion-panels class="transparent-background">
      <v-expansion-panel
        v-for="question in questions"
        :key="question.index"
        class="transparent-background"
      >
        <FaqComponent :question="question" class="transparent-background" />
      </v-expansion-panel>
    </v-expansion-panels>
  </v-col>
</template>

<script>
import { reactive, toRefs } from '@vue/composition-api'

import questions from '@/static/faqs.json'
import FaqComponent from '@/components/FaqComponent.vue'

export default {
  name: 'FAQs',
  components: {
    FaqComponent,
  },
  setup() {
    const state = reactive({
      questions,
    })

    return {
      ...toRefs(state),
    }
  },
}
</script>
