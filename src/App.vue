<template lang="html">
  <div>
    <h1>Countries of the World</h1>
    <div class="main-container">
      <countries-select :countries='countries'></countries-select>
      <countries-list :countries='countries'></countries-list>
      <country-detail class="country_detail" :country='selectedCountry'></country-detail>
    </div>
  </div>
</template>

<script>
// import CountriesSelect from './components/CountriesSelect.vue';
import CountryDetail from './components/CountryDetail.vue';
import CountriesList from './components/CountriesList.vue';
import { eventBus } from './main.js';

export default {
  name: 'app',
  data(){
    return {
      countries: [],
      selectedCountry: null
    }
  },
  mounted(){
    fetch('https://restcountries.eu/rest/v2/all')
    .then(res => res.json())
    .then(countries => this.countries = countries);

    eventBus.$on('country-selected', (country)=>{
      this.selectedCountry = country;
    });
  },
  components: {
    "countries-list": CountriesList,
    "country-detail": CountryDetail,
    // "country-select": CountrySelect
  }
}
</script>

<style lang="css" scoped>
.main-container {
    display: flex;
    justify-content: space-around;
  }



</style>
