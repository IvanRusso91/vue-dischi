<template>
  <div>
    <HeaderComp />

    <MainComp />
  </div>
</template>

<script>

import HeaderComp from './components/HeaderComp';
import MainComp from './components/MainComp'


export default {
  name: 'App',
  components: {
    HeaderComp,
    MainComp,

  }
}
</script>

<style lang="scss">

@import './assets/style/general';
@import './assets/style/vars';


</style>
