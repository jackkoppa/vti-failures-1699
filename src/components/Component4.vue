<template>
  <p>{{ myData }}</p>
</template>

<script lang="ts">
import Vue from 'vue';

export default Vue.extend({
  name: 'Component4',
  data() {
    return { myData: 'Hello 4' }
  }
});
</script>