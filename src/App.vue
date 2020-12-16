<template>
  <div id="app">
     <router-view></router-view>
      <maintabbar></maintabbar>
  </div>
</template>



<script>
import Maintabbar from './components/content/mainTabbar/Maintabbar.vue'



export default {

  name: 'App',

  components: {

      Maintabbar

  }

}

</script>



<style>
@import url("assets/css/base.css");



</style>
