<script setup lang="ts">

</script>

<template>
<div>
  <div class="topMenu">
    <nuxt-link to="/"> Home </nuxt-link>
    <nuxt-link to="/page-1"> Page 1 </nuxt-link>
    <nuxt-link to="/page-2"> Page 2 </nuxt-link>
    <nuxt-link to="/movie"> Page Movie </nuxt-link>
  </div>
  <slot/>

  <div class="footer">
    <p> My Web Site </p>
  </div>
</div>
</template>

<style scoped>
.topMenu{
  background-color: red;
}
.topMenu>a{
  text-decoration: none;
  color:white;
  padding: 10px;
  cursor: pointer;
}

.footer{
  background-color: blue;
  color:white;
}

</style>