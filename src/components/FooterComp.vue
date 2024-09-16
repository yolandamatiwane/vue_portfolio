<template>
    <footer>
    <p>
        Yolanda Matiwane &copy; {{ displayYear }}
    </p> 
    </footer>
        
</template>
<script>
export default {
    data(){
    return {
      currentYear: new Date()
    }
  },
  computed:{
    displayYear(){
      return this.currentYear.getFullYear()
      }
    }
}
</script>
<style scoped>
  footer{
    color: #bb7aad;
    background-color: #36454f00;
    bottom: 0;
    position: relative;
    margin: auto;
  }
</style>