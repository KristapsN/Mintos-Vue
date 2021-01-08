<template>
  <div class="checkbox--tag">
    <span class="checkbox--tag--close" @click="$emit('onClick')">x</span>
    <span class="checkbox--tag--name">{{ currencyName }}</span>
  </div>
</template>
<script lang='ts'>
import { defineComponent } from "vue";

const Component = defineComponent({
  props: {
    id: String,
    currencyName: String,
  },
});
export default Component;
</script>
<style scoped>
@import "./components.scss";
</style>