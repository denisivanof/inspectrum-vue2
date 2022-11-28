<template>
  <div class="app">
    <NavBar/>
    <Staff/>
  </div>
</template>

<script>


import Staff from "@/pages/Staff";
import NavBar from "@/components/NavBar";
export default {
  name: 'App',
  components: {NavBar, Staff},
}
</script>


<style>
@import "style/style.scss";
.app{
  display: flex;
  height: 100vh;
}
</style>
