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
    
</style>