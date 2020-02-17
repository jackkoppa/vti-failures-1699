<template>
  <p>{{ myData }}</p>
</template>

<script lang="ts">
import Vue from 'vue';

export default Vue.extend({
  name: 'Component5',
  data() {
    return { myData: 'Hello 5' }
  }
});
</script>