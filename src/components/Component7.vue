<template>
  <p>{{ myData }}</p>
</template>

<script lang="ts">
import Vue from 'vue';

export default Vue.extend({
  name: 'Component7',
  data() {
    return { myData: 'Hello 7' }
  }
});
</script>