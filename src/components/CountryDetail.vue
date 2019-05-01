<template lang="html">
<div v-if="country">
  <h2>{{country.name}}</h2>
  <p>Region: {{country.region}}</p>
  <p>Capital: {{country.capital}}</p>
  <p>Population: {{country.population}}</p>
  <img class="flag" :src="country.flag">
</div>
</template>

<script>
export default {
  name: 'country-detail',
  props: ['country']
}
</script>

<style lang="css" scoped>
.flag{
  height: 250px;
  padding: 1pt;
  background-color: black;
}

.country_detail{
  position: fixed;
  left: 40%;
}

.h2 .p {
  font-style: tahoma, sans-serif;
}

</style>
