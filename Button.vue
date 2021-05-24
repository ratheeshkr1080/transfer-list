<template>
  <button class="primary">{{ label }}</button>
</template>
<script>
export default {
  name: "Button",
  props: {
    label: String,
    size: String,
  },
};
</script>

<style scoped>
.primary {
  background-color: #f5f5f5;
  width: 62px;
  height:30px;
  margin: 15px 0;
  border: 1px solid black;
  border-radius: 5px;
}
</style>