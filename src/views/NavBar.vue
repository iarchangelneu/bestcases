<template>
  <div class="navbar">
      <a href="/" :class="['navbar__btn', {'active': currentPage == '/'}]">Главная</a>
      <a href="/#FAQ" :class="['navbar__btn']">FAQ</a>
      <router-link to="shop" :class="['navbar__btn', {'active': currentPage == '/shop'}]">Магазин</router-link>
      <router-link to="cases" :class="['navbar__btn', {'active': currentPage == '/cases'}]">Кейсы</router-link>
    </div>
</template>

<script>
export default {
  computed:{
    currentPage(){
      return this.$route.path;
    }
  }
}
</script>

<style scoped>
.navbar__btn {
  margin-right: 2.24vw;
  font-size: 1.250vw;
  font-weight: 300;
  color: #fff;
}
.active {
color:rgba(241, 90, 36, 0.6);
background: linear-gradient(176.7deg, rgba(241, 90, 36, 0) 38.92%, rgba(241, 90, 36, 0.6) 97.28%);
}
@media screen and (max-width: 480px){
.navbar__btn {
  font-size: 3vw;  
}
}
</style>