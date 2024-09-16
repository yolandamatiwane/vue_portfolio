<template>
  <div id="mainAboutDiv">  
    <h1>
      About Me:
    </h1> 
    <div class="card">
      <div class="container text-center">
        <div class="row">
          <div class="col-sm-8 lg-12">
            <div class="card-text">
              Hi, I'm Yolanda Matiwane. I graduated high school in 2018 and initially embarked on a journey at the University of Cape Town with aspirations of becoming an astrophysicist. It was during this time that I was first introduced to the world of programming, using VPython to create simulations of cosmic phenomena. This experience ignited a passion in me for coding and the incredible potential it holds.
              <br>
              <br>
              Though my university journey was cut short due to financial constraints, I discovered a new path through coding bootcamps. These experiences have revealed a deep-seated enthusiasm for web development, allowing me to bring my creative ideas to life through code.
              <br>
              <br>
              Today, I am dedicated to crafting engaging and functional websites, and I am continually inspired by the endless possibilities that coding offers.
            </div>

          </div>
          <div class="col-sm-4 lg-12">
            <img src="https://yolandamatiwane.github.io/vueProjectImages/20240422_122336.jpg">
          </div>
          <div id="skillDiv">
                <div>
                    <h4>Coding Skills</h4>
                    <div v-for="skill in skillsData" :key="skill.name" >
                        <h5>
                            <span>></span> {{ skill.name }}
                        </h5>  
                    </div>
                </div>
                <div>
                    <h4>Soft Skills</h4>
                    <h5>
                        <span>></span> Problem-Solving and Critical Thinking
                    </h5>
                    <h5>
                        <span>></span> Adaptability
                    </h5>
                    <h5>
                        <span>></span> Effective Communication
                    </h5>
                    <h5>
                        <span>></span> Team Collaboration
                    </h5>
                    <h5>
                        <span>></span> Time Management
                    </h5>
                    <h5>
                        <span>></span> Networking
                    </h5>
                </div>
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
      },
      skillsData(){
        return this.$store.state.skills
      }
    }
}
</script>
<style scoped>

  img{
    width:250px;
    height:250px;
    border-radius:20%;
    /* margin-left:600px; */
    box-shadow: 4px 4px 2px white;
    /* border: 4px solid rgba(153, 116, 150, 0.3); */
  }
  .col-sm-8 {
    box-shadow: 4px 4px 2px white;
    background-color: rgba(255, 255, 255, 0);
    border-radius: 10px;
  }
  #mainAboutDiv {
    font-family:"Bangers";
  }
  h1{
    font-size: 50px;
    color: #bb7aad;
    text-shadow: 2px 2px 4px #000000;
  }
  .card{
    /* color: white; */
    padding:10px;
    height:450px;
    background-color:rgb(204, 192, 255);
    width:90%;
    border:none;
    margin-top:0px;
    text-shadow: 2px 2px 4px rgb(163, 163, 163);
    /* margin-left:90px; */
    
  }
  span{
    color: #a01684;
    font-size: 20px;
  }
  #skillDiv{
    margin-top: 20px;
    display: flex;
    flex-wrap: wrap;
    justify-content: space-evenly;
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
