<template>
  <main>

    <div>

      <AlbumComp/>

    </div>

  </main>
</template>

<script>
import axios from 'axios'
import AlbumComp from './AlbumComp.vue'

export default {


  name: 'MainComp',

  components:{

    AlbumComp
  },
  
  data(){
    return{

      arrayAlbum: '',
    
    }
    
  },

  mounted(){

    this.getData()
  
  },

  methods:{
    
    getData(){

      axios.get('https://flynn.boolean.careers/exercises/api/array/music').then( (response) =>{

        this.arrayAlbum = response.data.response
      
      }) 

    }
  }
}


</script>

<style scoped lang="scss">

  main{
    background-color: rgba(30, 45, 59, 1);
  }
</style>
