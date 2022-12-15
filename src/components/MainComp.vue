<template>
  <main>

    <div class="ms-cont-70">

      <select @change="funzioneComputed()" v-model="sceltaGenere">
        <option value="">Tutti</option>
        <option :value="elem" v-for="(elem,index) in arrayGeneri" :key="index">{{elem}}</option>
      </select>


      <div class="ms-albums">

      <AlbumComp v-for="(elem,index) in funzioneComputed" 
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

      sceltaGenere: '',
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
          
        }
        
      })
      
    }) 
  
  },

  computed: {

    funzioneComputed(){

      if(this.sceltaGenere == ''){

        return this.arrayAlbum

      }else {

        return this.arrayAlbum.filter((elem) => {

          return elem.genre == this.sceltaGenere
        })
      }
    }
  }

}


</script>

<style scoped lang="scss">

  main{

    padding-top: 6rem;
    background-color: rgba(30, 45, 59, 1);
    height: calc(100% - 100px);
    overflow: auto;
    
    .ms-cont-70{

      width: 70%;
      margin: 0 auto;

      select{

        margin-bottom: 20px;
        width: 100px;
      }
    }

    .ms-albums{

      display: flex;
      flex-wrap: wrap;
      justify-content: start;
      gap: 20px 40px;
    }
  }
</style>
