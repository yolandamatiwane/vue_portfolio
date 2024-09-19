<template>
  <div id="mainAboutDiv">  
    <h1>
      About Me:
    </h1> 
    <div class="card">
      <div class="container text-center">
        <div class="row">
          <div class="col-sm-4 lg-12">
            <img src="https://yolandamatiwane.github.io/vueProjectImages/20240422_122336.jpg">
          </div>
          <div class="col-sm-8 lg-12">
            <h5 class="card-text">
              Hello! I'm Yolanda Matiwane, a passionate developer from Langa with a love for creating and problem-solving. 
              My coding journey began in 2020 with visual Python in a physics class, sparking my fascination with transforming ideas into functional applications. 
              Although I'm early in my career, I'm eager to expand my skills and tackle new challenges. 
              When I'm not coding, I enjoy reading, watching movies, and gaming, all of which fuel my creativity. 
              I'm excited to grow as a developer and contribute to innovative tech solutions.
            </h5>
          </div>
          <br>
          <h3><span class="cursor">></span>Skills</h3>
          <div id="skills">
            <div class="row" id="skillD">
              <div class="col-6" id="codingS">
                <h4>Coding Skills</h4>
                <div v-for="skill in skillsData" :key="skill.name" >
                  <h5>
                    <span>></span> {{ skill.name }}
                  </h5>  
                </div>
              </div>
              <div class="col-6">
                img/icon
              </div>
            </div>
            <!-- soft skills -->
            <div class="row">
              <div class="col-6">
              img
              
              </div>
              <div class="col-6" id="softS">
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
    width:200px;
    height:200px;
    border-radius:20%;
  }
  .col-sm-8 {
    /* box-shadow: 4px 4px 2px black; */
    background-color: rgba(255, 255, 255, 0);
    border-radius: 10px;
    align-items: center;
    color: white;
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
  #skills{
    align-items: center;
    justify-content: center
  }
  #skillD{
    /* margin-top: 30px; */
    display: flex;
    /* flex-wrap: wrap; */
    /* justify-content: space-evenly; */
  }
  .cursor{
    font-size:30px;
    animation: blink-caret 0.75s step-end infinite;
  }
  @keyframes blink-caret {
    from, to { border-color: transparent; }
    50% { border-color: white; }
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
