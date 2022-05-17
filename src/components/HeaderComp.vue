<template>
  <div class="container-fluid d-flex ir-head">
    <img src="../assets/img/logo-small.svg" alt="">

    <div class="dropdown btn-box">
      <button class="btn ir-btn dropdown-toggle" type="button" id="dropdownMenuButton1" data-bs-toggle="dropdown" aria-expanded="false">
        Seleziona un genere
      </button>
      <ul class="dropdown-menu" aria-labelledby="dropdownMenuButton1">
        <li><a class="dropdown-item" href="#">Action</a></li>
        <li><a class="dropdown-item" href="#">Another action</a></li>
        <li><a class="dropdown-item" href="#">Something else here</a></li>
      </ul>
</div>
  </div>
</template>

<script>
export default {
  nome: 'HeaderComp',
}
</script>

<style lang="scss" scoped>

@import '../assets/style/general';
@import '../assets/style/vars';


.ir-head{
  height: 80px;
  justify-content: space-between;
  background-color: $primary-color;
  img{
    transform: scale(0.5);  
  }
  
  .btn-box{
    margin-top: 20px;
    margin-right: 15px;
    .ir-btn{
      background-color: white;
    }
  }
}



</style>