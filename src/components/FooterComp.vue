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

footer {
    /* color: #bb7aad; */
    /* background-color: #36454f; */
    /* position: fixed; */
    font-weight: 700;
    bottom: 0;
    left: 0;
    width: 100%;
    height: 30px;
    text-align: center;
    padding: 10px;
    /* box-shadow: 0 -2px 5px rgba(0, 0, 0, 0.3); */
    font-size: 20px;
  }
  @media (max-width: 768px) {
    footer {
      font-size: 12px;
      padding: 8px;
    }
  }
</style>