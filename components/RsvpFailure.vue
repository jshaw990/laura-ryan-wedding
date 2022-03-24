<template>
  <div>
    <div class="small-title">There was an issue with your response</div>
    <div>Please resubmit your information</div>
    <div class="my-2" v-if="error">Error: {{ error }}</div>
  </div>
</template>

<script>
export default {
  name: 'RsvpFailure',
  props: ['error'],
}
</script>
