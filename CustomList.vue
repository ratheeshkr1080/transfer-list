<template>
  <div>
    <div class="choices" v-if="enhanced">
      <input
        type="checkbox"
        id="jack"
        value="Jack"
        v-on:click="handleToggleAll(items)"
      />
      <label for="Choices">Choices : </label>
      <label for="Choices">{{
        `${numberOfChecked(items)}/${items.length} selected`
      }}</label>
    </div>
    <div :key="initValue.id" v-for="initValue in items">
      <ListItem :name="initValue.name" :value="initValue.value" />
    </div>
  </div>
</template>
<script>
export default {
  name: "CustomList",
  props: {
    title,
    items,
  },
};
</script>

<style scoped>
</style>