<template>
  <p>{{ myData }}</p>
</template>

<script lang="ts">
import Vue from 'vue';

export default Vue.extend({
  name: 'Component9',
  data() {
    return { myData: 'Hello 9' }
  }
});
</script>