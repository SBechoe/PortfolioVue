<template>
  <div>
   <h3>Dit is About Me</h3>
   <ul class="list-group">
    <li class="list-group-item"
    @click="showPerson(person)"
    v-for="person in data.people" :key="person.id">
      <span :id="person.id"
      :title="person.firstName">
      {{ person.id }} - {{ person.firstName }}
      </span>
    </li>
    </ul>
  </div>
 </template>

 <script>
 import data from '../data/data';
 export default {
     name: 'AboutMe',
     data(){
       return {
         data
       }
     },
     methods: {
       showPerson(person) {
         this.$router.push({
          name: 'moreInfo',
          params: {
            id: person.id,
            firstName: person.firstName
        }
      })
      }
   }
}
 </script>

 <style lang="css" scoped>
 </style>
