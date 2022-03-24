<template>
  <div>
    <v-expansion-panel-header color="rgba(92, 20, 39, 0.75)">
      {{ question.title }}
    </v-expansion-panel-header>
    <v-expansion-panel-content
      color="rgba(92, 20, 39, 0.75)"
      v-html="question.content"
    >
    </v-expansion-panel-content>
  </div>
</template>

<script>
export default {
  name: 'FAQsComponent',
  props: ['question'],
}
</script>
