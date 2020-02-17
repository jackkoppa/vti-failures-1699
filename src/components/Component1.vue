<template>
  <p>{{ myData }}</p>
</template>

<script lang="ts">
import Vue from 'vue';

export default Vue.extend({
  name: 'Component1',
  data() {
    return { myData: 'Hello 1' }
  }
});
</script>