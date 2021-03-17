<template>
  <div>
    <h2>Showing People Info</h2>
    <div v-if="person">
        <ul class="list-group">
        <li class="list-group-item">Naam: {{ person.firstName }} {{ person.lastName }}</li>
        <li class="list-group-item">Leeftijd: {{ person.age }}</li>
        <li class="list-group-item">
          Profielfoto: 
          <img :src="getImgUrl(person.img)"
               :alt="person.img"
               class="img-fluid">
        </li>
        <li class="list-group-item">{{ person.info }}</li>
      </ul>
    </div>
  </div>
</template>

<script>
import data from '../data/data';

export default {
  name: 'MoreInfoComponent',
  data(){
    return {
      data
    }
  },
  created() {
    // Set the simple parameters
    this.id = this.$route.params.id;
    this.name = this.$route.params.firstName;

    // fetch the correct country from the loaded data
    this.person = this.data.people.find(c => c.id === +this.id);
  },
    methods: {
    getImgUrl(img) {
      return require('../assets/' + img);
    }
  }
}
</script>

<style lang="css" scoped>
</style>
