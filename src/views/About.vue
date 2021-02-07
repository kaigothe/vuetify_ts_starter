<template>
  <div class="about">
    <h1>This is an about page</h1>
    <v-sheet outlined rounded class="text-center py-4 my-4" v-if="loader">
      <v-progress-circular
        indeterminate
        color="primary"
      ></v-progress-circular>
    </v-sheet>
    <v-sheet outlined rounded class="text-center py-4 my-4" v-if="!loader">
      <p class="text--secondary"> {{message}}</p>
    </v-sheet>
  </div>
  
</template>



<script lang="ts">
import { Component, Vue } from 'vue-property-decorator';

@Component
export default class Home extends Vue {

  loader: boolean = true
  message: string = ''

  mounted() {
    this.myFunction()
  }
  

  /** Custom Functions
   * 
   */

  myFunction(){
    setTimeout(()=>{
      this.loader = false,
      this.message = 'The navigation drawer will appear from the bottom on smaller size screens.'
    }, 800)
  }

}
</script>
