<template lang="html">
  <div>
    <select class="" name="">
      <option disabled value="">Select a Country</option>
      <option v-for="country in countries" :value="country">{{country.name}}</option>
    </select>
  </div>
</template>

<script>
import ListItem from './ListItem.vue';

export default {
  name: 'countries-select',
  props: ['countries'],
  components: {
    "option": ListItem
  }
}
</script>

<style lang="css" scoped>
</style>
