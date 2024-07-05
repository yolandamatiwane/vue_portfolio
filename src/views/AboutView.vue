<template>
  <div id="mainAboutDiv">  
    <h1>
      About Me:
    </h1> 
    <div class="card">
      <div class="container text-center">
        <div class="row">
          <div class="col-sm-8 lg-12">
            <h5 class="card-text">
              Hey there, I'm <span>Yolanda Matiwane</span>, and I'm passionate about <span>creating and problem-solving</span>. Originally from <span>Langa</span>, I graduated from high school in 2018 and have since embarked on an exhilarating journey into the world of <span>coding</span>.
              <br>
              My fascination with coding began in <span>2020</span> when I encountered <span>visual Python</span> in a physics class. Witnessing how <span>code can transform into tangible creations</span> sparked my curiosity for <span>understanding how things work</span> and the <span>excitement of bringing ideas to life</span> through <span>visualizations</span> and <span>functional applications</span> .
              <br>
              While I'm still in the <span>early stages of my coding career</span>, I'm driven by a desire to <span>expand my skills and knowledge</span>. I thrive on <span>tackling challenges</span> and continuously <span>explore new concepts</span> to deepen my understanding of <span>programming</span>. Beyond coding, I find inspiration in <span>reading, movies, and gaming</span>, activities that fuel my <span>creativity</span> and enrich my <span>perspective</span>.
              <br>
              My goal is to <span>evolve as a developer</span>, transforming my ideas into <span>impactful projects</span>. I'm enthusiastic about the <span>endless possibilities that coding offers</span> and eagerly anticipate contributing to <span>innovative solutions</span> within the <span>tech industry</span>.
            </h5>
            <h6>For more? please feel free to contact me</h6>
          </div>
          <div class="col-sm-4 lg-12">
            <img src="https://yolandamatiwane.github.io/vueProjectImages/20240422_122336.jpg">
          </div>
        </div>
      </div>
    </div>
  </div>
</template>
<script>
export default {
    computed: {
      pageAboutData(){
        return this.$store.state.aboutMe
      }
    }
}
</script>
<style scoped>
  img{
    width:300px;
    height:300px;
    border-radius:50%;
    /* margin-left:600px; */
    box-shadow:10px 10px 5px black;
    border: 4px solid rgba(153, 116, 150, 0.3);
  }
  .col-sm-8 {
    box-shadow:10px 10px 5px black;
    background-color: rgba(153, 116, 150, 0.3);
    border-radius: 10px;
  }
  #mainAboutDiv {
    margin: 60px;
    font-family:"Bangers";
  }
  h1{
    font-size: 100px;
    color: #bb7aad;
    text-shadow: 2px 2px 4px #000000;
  }
  .card{
    /* color: white; */
    padding:50px;
    height:450px;
    background-color:rgb(204, 192, 255);
    width:90%;
    border:none;
    margin-top:20px;
    text-shadow: 2px 2px 4px rgb(163, 163, 163);
    /* margin-left:90px; */
    
  }
  span{
    color: #a01684;
    font-size: 20px;
  }
  /* Responsiveness */
  @media only screen and (max-width: 768px) {
    /* Adjust layout for smaller screens */
    #mainAboutDiv {
      margin: 20px;
      padding: 10px;
    }
   .card {
      padding: 20px;
      height: auto;
      width: 90%;
    }
   .col-sm-8 {
      margin-bottom: 20px;
    }
    img {
      width: 100%;
      height: auto;
      margin: 0 auto;
    }
    h1 {
      font-size: 60px;
    }
    h5 {
      font-size: 18px;
    }
    h6 {
      font-size: 14px;
    }
  }

  @media only screen and (max-width: 480px) {
    /* Adjust layout for even smaller screens */
    #mainAboutDiv {
      margin: 10px;
      padding: 5px;
    }
   .card {
      padding: 10px;
      height: auto;
      width: 90%;
    }
   .col-sm-8 {
      margin-bottom: 10px;
    }
    img {
      width: 100%;
      height: auto;
      margin: 0 auto;
    }
    h1 {
      font-size: 40px;
    }
    h5 {
      font-size: 14px;
    }
    h6 {
      font-size: 12px;
    }
  }
</style>
