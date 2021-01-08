<template>
  <div class="checkbox--button">
      <label :for="id">
      <input 
        type="checkbox"
        :value="currencyName"
        @change="$emit('update:currencyName', $event.target.value)"
      >
      {{currencyName}}</label>
  </div>
</template>
<script lang='ts'>
import { defineComponent } from 'vue';

const Component = defineComponent({
  props: {
    id: String,
    currencyName: String,
    type: {
      type: String,
      required: true,
    },
  },
});
export default Component;
</script>
<style scoped>
  @import './components.scss';
</style>