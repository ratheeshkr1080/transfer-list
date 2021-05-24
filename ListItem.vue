<template>
  <!-- <div class="list-item">
    <input type="checkbox" id="" value=""  />
    <label for="name">{{ name }}</label>
  </div> -->
  <div class="list-item" v-if="checked">
    <input
      type="checkbox"
      id=""
      value=""
      checked
    />
    <label for="name">{{ name }}</label>
  </div>
  <div class="list-item" v-else>
    <input type="checkbox" id="" value="" />
    <label for="name">{{ name }}</label>
  </div>
</template>
<script>
export default {
  name: "ListItem",
  props: {
    name: String,
    value: String,
    checked: Boolean,
    indeterminate: Boolean,
  },
};
</script>
<style scoped>
.list-item {
  font-family: "Courier New", Courier, monospace;
  font-size: 20px;
  font-weight: normal;
  margin: 10px;
}
</style>