<template>
  <div class="grid">
    <Card v-for="project in filteredProjects" :key="project.id" :project="project" />
  </div>
</template>

<script>
import Card from './components/Card.vue';
import { projects } from './data.json';
export default {
  components: {
    Card
  },
  data() {
    return {
      projects: []
    };
  },
  computed: {
    filteredProjects() {
      return this.projects.filter(project => {
        return project.fields.includes('Game Design');
      });
    }
  },
  mounted() {
   this.projects = projects 
//     fetch(process.env.DATA_JSON_URL,{
//   method: 'GET',
//   mode: 'cors',
//   headers: {
//     'Content-Type': 'application/json',
//     'Access-Control-Allow-Origin': '*' // Allow requests from any origin
//   }
// })
//       .then(response => response.json() )
//       .then(data => {
//         this.projects = projects //data.projects;
//       })
//       .catch(error => {
      //  console.error('Error fetching data:', error);
      //});
  }
};
</script>