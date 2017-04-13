<template>
  <div id="app">
    <NavBar/>
    <div> <router-view></router-view> </div>
    <Footer/>
  </div>

</template>

<script>
import NavBar from './components/NavBar.vue'
import Footer from './components/Footer.vue'
export default {
  name: 'app',
  components: {
    NavBar, Footer}
}
</script>

<style>
#app {
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
}
html, body{
  height: 100%;
  font-family: 'Source Sans Pro', 'Helvetica Neue', Arial, sans-serif !important;
}
.warp{
  height: 100%;
  margin: 0 auto;
}
/* 超小屏幕（手机，小于 768px） */
@media (max-width: 768px) {
  .warp{
 
  width: calc(100% - 6px);
}}

/* 小屏幕（平板，大于等于 768px） */
@media (min-width: 768px) {
   .warp{
 
  width: 750px;
}}

/* 中等屏幕（桌面显示器，大于等于 992px） */
@media (min-width: 992px) { 
  .warp{
  width: 950px;
} }
@media (min-width: 1200px) { 
  .warp{
  width: 1100px;
} }
/* 大屏幕（大桌面显示器，大于等于 1200px） */
@media (min-width: 1500px) { 
  .warp{
  width: 1400px;
}}

</style>
