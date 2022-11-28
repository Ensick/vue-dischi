<template>
  <main>

    <div class="ms-cont-70">

      <select name="" id="" v-model="valueOptionSelected">
        <option @click="selezioneGenere()" :value="elem" v-for="(elem,index) in arrayGeneri" :key="index">{{elem}}</option>
      </select>


      <div class="ms-albums">

      <AlbumComp v-for="(elem,index) in arrayAlbum" 
      :key="index" 
      :AlbumData = "elem"/>

      </div>

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

      sceltaGenere: false,
      valueOptionSelected: '',
      arrayAlbum: [],
      arrayGeneri: [],
    
    }
    
  },

  mounted(){

    axios.get('https://flynn.boolean.careers/exercises/api/array/music').then( (response) =>{

      this.arrayAlbum = response.data.response

      this.arrayAlbum.forEach((singoloAlbum) =>{

        if(!this.arrayGeneri.includes(singoloAlbum.genre)){

          this.arrayGeneri.push(singoloAlbum.genre)

          console.log(this.arrayGeneri);
          
        }
        
      })
      
    }) 
  
  },

  methods:{


  }

}


</script>

<style scoped lang="scss">

  main{

    padding-top: 6rem;
    background-color: rgba(30, 45, 59, 1);
    
    .ms-cont-70{

      width: 70%;
      margin: 0 auto;
    }

    .ms-albums{

      display: flex;
      flex-wrap: wrap;
      justify-content: space-between;
      gap: 20px 40px;
    }
  }
</style>
