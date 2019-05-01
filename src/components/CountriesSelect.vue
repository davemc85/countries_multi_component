<template lang="html">
  <div>
    <select >
      <option disabled selected value="">Select a Country</option>
      <option v-for="(country, index) in countries" :country="country" :key="index">{{country.name}}</option>
    </select>
  </div>
</template>

<script>
import SelectItem from './SelectItem.vue';

export default {
  name: 'countries-select',
  props: ['countries'],
  components: {
    "select-item": SelectItem
  },

}
</script>

<style lang="css" scoped>
</style>
