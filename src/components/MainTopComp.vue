<template>
  <div class="container-fluid ir-head ">
    <div class="row">
      <div class="col-6 left">
        <img src="../assets/img/logo-small.svg" alt="">
      </div>

      <div class="col-6 right">

        <select name="form-control my-3" 
                v-model="dropGenre"
                @change= "$emit('type',dropGenre);
">
                
          <option value="">Seleziona un genere</option>
          <option value="Rock">Rock</option>
          <option value="Pop">Pop</option>
          <option value="Jazz">Jazz</option>
          <option value="Metal">Metal</option>
        </select>

      </div>
    </div>
  </div>
  
</template>

<script>
export default {
  nome: 'MainTopComp',
  data(){
    return{
      dropGenre : '',
    }
  },
  
  methods:{
    
    
  },
}  
</script>

<style lang="scss" scoped>

@import '../assets/style/general';
@import '../assets/style/vars';


.ir-head{
  height: 80px;
  background-color: $primary-color;
  .row{
    .left{
    padding: 10px 20px;
    img{
      width: 50px;
      filter: invert(30%) sepia(10%) saturate(2500%) hue-rotate(80deg) brightness(110%) contrast(80%); 
    }
  } 
  .right{
    display: flex;
    justify-content: flex-end;
    align-items: center;

    select{
      color: white;
      padding: 10px 20px;
      margin-right: 20px;
      border-radius: 10px;
      background-color: rgb(85, 165, 85);
    }

  }

  }
  
  
  .btn-box{
    margin-top: 20px;
    margin-right: 15px;
    .choice{
     width: 300px;
    }
  }
}



</style>