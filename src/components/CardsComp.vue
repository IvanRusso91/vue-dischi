<template>

  <div class="ir-card">
    <div class="cardimg">
      <img src="" alt="">

      <div class="testo">
        <h3>nome</h3>
        <p>artista <br> anno</p>
      </div>
    
    </div>
  </div>

</template>

<script>
export default {
  name:'CardsCopm',
}
</script>

<style lang="scss" scoped>

@import '../assets/style/general';
@import '../assets/style/vars';

.ir-card{
  width: 200px;
  height: 300px;
  margin-top: 80px;
  background-color:$primary-color;
  .cardimg{
    width: 160px;
    height: 160px;
    margin: 16px;
    background-color: rgb(0, 17, 255);
  }
  .testo{
    color: $third-color;
    text-align: center;
    margin-top: 150px;
    h3{
      color: white;
    }
  }
}

</style>