<template>
<div>

  <MainTopComp @type = "genreSelect" />

  <div class="sfondo">
    <div class="container d-flex ir-dischi">

      <div v-if="isLoading" class="load">
        <img src="https://giffiles.alphacoders.com/307/30777.gif" alt="">

        <h1>Loading.....</h1>
      </div>
      <CardsComp
      v-else
      v-for="(item, index) in filterGenreAlbum" :key="`disc-${index}`"
      :discs = "item"/>

    </div>
  </div>
</div>  
</template>

<script>
import axios from 'axios';
import CardsComp from '@/components/CardsComp'
import MainTopComp from '../components/MainTopComp';

export default {
  name:'MainComp',
  components :{
    CardsComp,
    MainTopComp,
  },
  data(){
    return{
      baseUrl:'https://flynn.boolean.careers/exercises/api/array/music',
      discsArray: [],
      isLoading: true,
      selectType:'',
      albumGenre :[],


    }
  },
  mounted(){
    this.getAPI()
  },

  methods:{
    getAPI(){
      axios.get(this.baseUrl)
      .then(r =>{
        console.log(r.data.response);
        this.discsArray = (r.data.response);
         setTimeout(()=>{
          this.isLoading = false;
          },3000)
      })
    },

    genreSelect(stringa){
      // console.log(stringa);
      this.selectType = stringa;
    },  
    

    genrePush(){
      this.discsArray.forEach(disc =>{
        if(!this.albumGenre.includes(disc.genre)){
          this.albumGenre.push(disc.genre);
        }
      });
    }
  },

  computed:{
    filterGenreAlbum(){
       let albumType = [];
       if(this.selectType === ''){
         albumType = this.discsArray
      }
       else{
         albumType = this.discsArray.filter(disc =>{
          return disc.genre.toUpperCase().includes(this.selectType.toUpperCase());
        })
      }
      return albumType;
    },
   
    
  },
 
};
</script>

<style lang="scss" scoped>

@import '../assets/style/general';
@import '../assets/style/vars';

.sfondo{
  height: calc(100vh - 80px);
  background-color: $secodary-color;

  .ir-dischi{
    flex-wrap: wrap;
    
    .load{
      margin-top: 100px;
      margin-left: 450px;
      h1{
        color: white;
        text-align: center;
        margin-top: 50px;
      }
    }
  }
}

</style>