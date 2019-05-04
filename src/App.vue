<template>
  <div id="app">
    <Navbar/>
    <router-view/>
  </div>
</template>

<script>
import Navbar from '@/components/modules/nav'
export default {
  name: 'App',
  components:{
    Navbar
  }
}
</script>

<style>
.container{
  padding: 0px;
  margin: 0px;
}

</style>
