<template>
  <div class="sfondo">
    <div class="container d-flex ir-dischi">

      <CardsComp
      v-for="(item, index) in discsArray" :key="`disc-${index}`"
      :discs = "item"/>

    </div>
  </div>
</template>

<script>
import axios from 'axios';
import CardsComp from '@/components/CardsComp'

export default {
  name:'MainComp',
  components :{
    CardsComp,
  },
  data(){
    return{
      baseUrl:'https://flynn.boolean.careers/exercises/api/array/music',
      discsArray: [],

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
      })
    }
  }
}
</script>

<style lang="scss" scoped>

@import '../assets/style/general';
@import '../assets/style/vars';

.sfondo{
  height: calc(100vh - 80px);
  background-color: $secodary-color;

  .ir-dischi{
    flex-wrap: wrap;
    
  }
}

</style>