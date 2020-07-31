<template>
  <div>
    <h1>Filters & Mixins</h1>
    <input v-model="filterText" type="text" />
    <ul>
      <li v-for="fruit in filteredFruits" :key="fruit.id">{{fruit}}</li>
    </ul>
  </div>
</template>

// filter is used in instances where you want to change the display of data without actually changing the data
// often times filtering through a computed property is more performant, reach for this when possible
// Mixin is shared logic
<script>
import { fruitMixin } from "./fruitMixin.js";
export default {
  mixins: [fruitMixin],
};
</script>

<style>
</style>
