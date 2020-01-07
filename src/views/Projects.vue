<template>
  <div class="projects">
   <h1 class="subheading grey--text">ทดสอบ</h1>   

   
   

   <v-container class="my-5">
    <v-expansion-panels>
      <v-expansion-panel v-for="(project, index) in myProjects" :key="index">
        <v-expansion-panel-header>{{ project.title }}</v-expansion-panel-header>
        <v-expansion-panel-content>
          {{ project.detail }}
        </v-expansion-panel-content>
      </v-expansion-panel>
    </v-expansion-panels>
   </v-container>
 </div> 
</template>

<script>
export default {
  data(){
    return {
      projects: [
        {title: 'Project1', detail: 'Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat.'},
        {title: 'Project2', detail: 'Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat.'},
        {title: 'Project3', detail: 'Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat.'},
        {title: 'Project4', detail: 'Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat.'},
        {title: 'Project1', detail: 'Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat.'}
      ]

    }
  },
  computed: {
    myProjects(){
      return this.projects.filter(project => {
        return project.title === 'Project1'
      })
    }
  }
}
</script>