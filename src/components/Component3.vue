<template>
  <p>{{ myData }}</p>
</template>

<script lang="ts">
import Vue from 'vue';

export default Vue.extend({
  name: 'Component3',
  data() {
    return { myData: 'Hello 3' }
  }
});
</script>