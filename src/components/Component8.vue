<template>
  <p>{{ myData }}</p>
</template>

<script lang="ts">
import Vue from 'vue';

export default Vue.extend({
  name: 'Component8',
  data() {
    return { myData: 'Hello 8' }
  }
});
</script>