<template>
  <div>
    <h2>Showing People Info</h2>
    <h3>Id: {{id}}</h3>
    <h3>First Name: {{firstName}}</h3>

    <div v-if="person">
        <ul class="list-group">
        <li class="list-group-item">{{ person.firstName }}</li>
        <li class="list-group-item">{{ person.lastName }}</li>
        <li class="list-group-item">{{ person.age }}</li>
        <!-- <li class="list-group-item">
          <img :src="getImgUrl(person.img)"
               :alt="person.img"
               class="img-fluid">
        </li> -->
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
  }
  //   methods: {
  //   getImgUrl(img) {
  //     return require('../assets/people/' + img);
  //   }
  // }
}
</script>

<style lang="css" scoped>
</style>
