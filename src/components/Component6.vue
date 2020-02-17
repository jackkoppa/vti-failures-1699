<template>
  <p>{{ myData }}</p>
</template>

<script lang="ts">
import Vue from 'vue';

export default Vue.extend({
  name: 'Component6',
  data() {
    return { myData: 'Hello 6' }
  }
});
</script>