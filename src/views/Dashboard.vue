<template>
  <main>
    <v-button type="submit">
      Send
    </v-button>
    <v-button type="cancel" :disabled="true">
      Cancel
    </v-button>
  </main>
</template>
<script>
  import VButton from '../components/Button'
  export default {
    components: {
      VButton
    }
  }
</script>
<style></style>
