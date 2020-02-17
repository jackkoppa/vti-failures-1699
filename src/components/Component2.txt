<template>
  <p>{{ myData }}</p>
</template>

<script lang="ts">
import Vue from 'vue';

export default Vue.extend({
  name: 'Component2',
  data() {
    return { myData: 'Hello 2' }
  }
});
</script>