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
  background-color:rgb(204, 192, 255);
  margin-bottom: 30px;
  height: 100%;
  margin-top: 80px;
}

</style>
