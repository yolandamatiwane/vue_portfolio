<template>
  <!-- <spinner-comp></spinner-comp> -->
  <div class="card" id="home">
    <div class="container text-start">
      <div class="row">
        <div class="col-lg-7 col-sm-12" id="homeText">
          <div>
            <h1 class="animate__animated animate__zoomIn">Good {{ timeOfDay }}</h1>
            <h2>I am <span>YOLANDA MATIWANE</span>...</h2>
            <h4>AN ASPIRING DEVELOPER</h4>
            <h2>  Welcome To My Portfolio!</h2>
            <p>
              <a href="/about" class="btn btn-outline-custom">More About Me</a>
              <a href="/contacts" class="btn btn-outline-light">Contact Me</a>
            </p>
          </div>
        </div>
        <div class="col-lg-5 col-sm-12" id="image">
          <div>
            <img src="https://yolandamatiwane.github.io/vueProjectImages/girl%20on%20laptop.png" class="img-fluid" id="under">
            <img src="https://yolandamatiwane.github.io/vueProjectImages/wobble%20gif.gif" class="img-fluid" id="overlapImg">
          </div>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
// import SpinnerComp from '@/components/SpinnerComp.vue';
export default {
  name: 'HomeView',
  data(){
    return {
      currentTime: new Date()
    }
  },
  computed:{
    timeOfDay(){
      let hour = this.currentTime.getHours()
      if(hour>= 5 && hour<12){
        return 'Morning'
      } else if(hour>=12 && hour < 18){
        return 'Afternoon'
      }else{
        return 'Evening'
      }
    }
  },
  components: {
  //  SpinnerComp
  }
}
</script>
<style scoped>
  #under{
    position:absolute;
    top:0;
    right:0;
    width:600px;
    margin-top:100px;
  }
  #overlapImg{
    position:relative;
    z-index:1;
    width:900px;
    height:500px;
    margin-left:20px;
  }
  #under, #overlapImg{
    object-fit: cover;
  }
  .btn-outline-custom, .btn-outline-light{
    margin-left:20px;
    height:60px;
  }
  .btn-outline-light{
    font-family: "Bangers";
    font-size: 20px;
    box-shadow: 2px 2px 4px;
    width:150px;
  }
  .btn-outline-custom{
    font-family:"Bangers";
    font-size: 20px;
    color: white;
    background-color: #670652;
    box-shadow: 2px 2px 4px;
    width: 200px ;
  }
  .btn-outline-custom:hover{
    background-color: white;
    color: #670652;
  }
  p{
    margin-top: 20px;
  }
  h1{
    font-family:"Bangers";
    font-size: 90px;
    color: #670652;
    text-shadow: 2px 2px 4px #000000;
  } 

  #homeText{
    margin-top: 50px;
  }
  #homeText div{
    margin-left: 30px;
  }
  h2,h4{
    font-family:"Bangers";
    /* font-weight:800; */
  }
  span{
    font-size: 50px;
  }
  span,h4{
    color:white;
  }
  #image{
    margin-top: 30px;
  }
  #home{
    display: flex;
    justify-content: space-between;
    margin-left: 30px;
    margin-top: 80px;
    align-content: center;
    /* margin: auto; */
    min-height: 400px;
    width: 95%;
    color: rgba(20, 0, 109, 0.705);
    font-weight: 900;
    background-color: rgba(153, 116, 150, 0);
    box-shadow: 10px 15px 5px;
    border: none;
  }
  @media only screen and (max-width:1150px){
    #under{
      width: 350px;
      margin-left: 100px;
      height: 300px;
    }
    h1{
      font-size: 70px;
    }
    span{
      font-size: 40px;
    }
    #overlapImg{
      height: 400px;
      width: 800px;

    }
  }
  /* for tablet screens */
  @media(max-width:995px){
    #under{
      margin: 0px;
    }
    #overlapImg{
      display: none;
    }
    #homeText, #image{
      justify-content: center;
    }
    #home{
      margin-top: 40px;
      /* height: 400px; */
    }
    #image{
      margin-top: 20px;
      width: 100%;
      height: auto;
    }
    .btn-outline-custom, .btn-outline-light {
      margin-left: 10px;
      height: 40px;
      font-size: 16px;
    }
    h1 {
      font-size: 60px;
    }
    h2, h4, span {
      font-size: 24px;
    }
  }
  @media(max-width:800px){
    #home div{
      text-align: center;
      align-items: center;
      width: 100%;
    }
    #homeText div{
      margin-left: 0px;
    }
    #under{
      position: relative;
    }
  }
  /* for mobile screens */
  @media(max-width:480px){
    #home{
      padding:0px;
      margin: auto;
    }
    #image{
      margin-top: 10px;
      margin-left:20px;
      width: 100%;
    }
    .btn-outline-custom, .btn-outline-light {
      margin-left: 5px;
      width: 100%;
      height: 30px;
      font-size: 18px;
    }
    h1{
      font-size: 36px;  
    }
    h2{
      font-size: 30px;
    }
    h4,span{
      font-size:26px;
    }
  }

</style>
