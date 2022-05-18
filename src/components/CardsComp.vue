<template>

  <div class="ir-card">
    <div class="cardimg">
      <img :src="discs.poster" :alt="discs.title">

      <div class="testo">
        <h5>{{discs.title}}</h5>
        <p>{{discs.author}} <br> {{discs.year}}</p>
      </div>
    
    </div>
  </div>

</template>

<script>
export default {
  name:'CardsCopm',
  props:{
    discs:Object,
  }
}
</script>

<style lang="scss" scoped>

@import '../assets/style/general';
@import '../assets/style/vars';

.ir-card{
  width: 220px;
  height: 370px;
  margin: 50px 30px 0px 0px;
  background-color:$primary-color;
  opacity: 0.7;
  transition: 1s;;
  &:hover{
    cursor: pointer;
    opacity: 1;
    transform: scale(1.1);
  }
 
  .cardimg{
    margin: 15px;
    img{
      width: 190px;
    }
  }
  .testo{
    text-align: center;
    margin-top: 15px;
    p{
      font-weight: bold;
      color: $third-color;
      font-size: 1.2rem;
    }
    h5{
      text-transform: uppercase;
      margin-bottom: 15px;
      color: white;
    }
  }
}

</style>