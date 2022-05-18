<template>
<div>

  <MainTopComp @gender: dropGender/>

  <div class="sfondo">
    <div class="container d-flex ir-dischi">

      <div v-if="isLoading" class="load">
        <img src="https://giffiles.alphacoders.com/307/30777.gif" alt="">

        <h1>Loading.....</h1>
      </div>
      <CardsComp
      v-else
      v-for="(item, index) in discsArray" :key="`disc-${index}`"
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
      albumGender:[],
      selectType:'',

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

    genderSelect(gender){
      // console.log(gender);
      this.selectType = gender;
      
    },

    genderPush(){
      this.discsArray.forEach(disc =>{
        if(!this.albumGender.includes(disc.genre)){
          this.albumGender.push(disc.genre);
        }
      });
      console.log(this.albumGender);
    }
  },

  computed:{
    filterGenderAlbum(){
      let albumType = []
      if(this.selectType === 'none'){
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