<template>
  <div class="sfondo">
    <div class="container d-flex ir-dischi">
      
    </div>

  </div>
</template>

<script>
export default {
  name:'MainComp',
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