<template>
  <v-app>
    <Index></Index>
  </v-app>
</template>

<script lang="ts">
import Vue from 'vue';
import Index from './views/Index.vue';

export default Vue.extend({
  name: 'App',

  components: {
    Index,
  },

  data: () => ({
    //
  }),
});
</script>
