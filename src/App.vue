<template>
  <navbar-comp/>
  <router-view/>
  <footer-comp/>

</template>

<script>
import NavbarComp from "./components/NavbarComp.vue"
import FooterComp from "./components/FooterComp.vue"


export default{
  
  components:{
    NavbarComp,
    FooterComp
  },
  computed:{
    getAboutMe(){
      return this.$store.dispatch('getAboutMe')
    }
  },
  mounted() {
    this.getAboutMe
  }
}
</script>

<style>

#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
}



body{
  /* background-image: url('https://slidescorner.com/wp-content/uploads/2022/09/01-Heidi-Pastel-Abstract-Organic-Shapes-Background-by-SlidesCorner.jpg');
  background-size: cover; */
  background-color:rgb(204, 192, 255);
}

</style>
