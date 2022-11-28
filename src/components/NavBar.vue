<template>
<section class="navbar">
  <div class="navbar__logo">
    <img :src="require('../assets/Logo.png')" alt="logo">
  </div>
</section>
</template>

<script>
export default {
  name: "NavBar",
}
</script>

<style scoped>
@import "../style/navbar.scss";
</style>