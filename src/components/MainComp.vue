<template>
  <div class="sfondo">
    <div class="container d-flex ir-dischi">

      <CardsComp />

    </div>
  </div>
</template>

<script>

import CardsComp from '@/components/CardsComp'

export default {
  name:'MainComp',
  components :{
    CardsComp,
  },
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