<template>
  <main>
    
  </main>
</template>

<script>
import axios from 'axios'

export default {
  name: 'MainComp',
  
  data(){
    return{

      arrayDischi: '',
    
    }
    
  },

  mounted(){

    this.getData()
  
  },

  methods:{
    
    getData(){

      axios.get('https://flynn.boolean.careers/exercises/api/array/music').then( (response) =>{

        this.arrayDischi = response.data.response
      
      }) 

    }
  }
}


</script>

<style scoped lang="scss">

</style>
