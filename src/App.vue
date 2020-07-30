<template>
  <div class="container">
    <div class="row">
      <div class="col-xs-12 col-sm-8 col-sm-offset-2 col-md-6 col-md-offset-3">
        <h1>Filters & Mixins</h1>
        <p>{{text | toUpperCase | toLowerCase}}</p>
        <p>{{text | toUpperCase}}</p>
        <hr />
        <input v-model="filterText" type="text" />
        <ul>
          <li v-for="fruit in filteredFruits" :key="fruit.id">{{fruit}}</li>
        </ul>
      </div>
    </div>
  </div>
</template>

// filter is used in instances where you want to change the display of data without actually changing the data

<script>
export default {
  data() {
    return {
      text: "Hello There!",
      fruits: ["apple", "banana", "mango", "melon"],
      filterText: "",
    };
  },
  filters: {
    toUpperCase(value) {
      return value.toUpperCase();
    },
  },
  computed: {
    filteredFruits() {
      return this.fruits.filter((element) => {
        return element.match(this.filterText);
      });
    },
  },
};
</script>

<style>
</style>
