<template>
  <div v-if="checked">
    <input type="checkbox" id="" value="" checked />
    <label for="name">{{ name }}</label>
  </div>
  <div v-else>
    <input type="checkbox" id="" value="" />
    <label for="name">{{ name }}</label>
  </div>
</template>
<script>
export default {
  name: "CheckBox",
  props: {
    name: String,
    value: String,
    onClick:()=>{},
    checked: Boolean,
    indeterminate:Boolean,
    disabled:Boolean,
  },
};
</script>
<style scoped>
</style>