<template>
  <div>
      <p>{{ myNestedData.title }}</p>
      <div v-for="level1 in myNestedData.data" :key="level1.title">
          <p>{{ level1.title }}</p>
          <div v-for="level2 in level1.data" :key="level2.title">
            <p>{{ level2.title }}</p>
            <div v-for="level3 in level2.data" :key="level3.title">
                <p>{{ level3.title }}</p>
                <div v-for="level4 in level3.data" :key="level4.title">
                    <p>{{ level4.title }}</p>
                </div>
            </div>
          </div>
      </div>
  </div>
</template>

<script lang="ts">
import Vue from 'vue';

interface NestedData {
    title: string
    data: NestedData[]
}

function getNestedData(depth: number, width: number, position = 0): NestedData {
    const nestedData: NestedData = { title: `depth-${depth}-width-${width}-position-${position}`, data: [] }
    if (depth > 0) {
        for (let i = 0; i < width; i++) {
            nestedData.data.push(getNestedData(depth - 1, width, i))
        }
    }
    return nestedData
}

export default Vue.extend({
  name: 'ComplexComponent5',
  data() {
    return { myNestedData: getNestedData(4, 3) }
  }
});
</script>