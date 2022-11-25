<template>
  <main>

    <div class="ms-cont-albums">

      <AlbumComp v-for="(elem,index) in arrayAlbum" 
      :key="index" 
      :AlbumData = "elem"/>

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

    padding-top: 6rem;
    background-color: rgba(30, 45, 59, 1);
    
    .ms-cont-albums{

      display: flex;
      flex-wrap: wrap;
      justify-content: space-between;
      gap: 20px 40px;
      width: 70%;
      margin: 0 auto;
    }
  }
</style>
