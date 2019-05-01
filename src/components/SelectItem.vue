<template lang="html">
  <option v-on:select="handleSelect">{{country.name}}</option>
</template>

<script>
import { eventBus } from '../main.js'
export default {
  name: 'select-item',
  props: ['country'],
  methods: {
    handleSelect: function(){
      eventBus.$emit('country-selected', this.country)
    }
  }
}
</script>

<style lang="css" scoped>
</style>
