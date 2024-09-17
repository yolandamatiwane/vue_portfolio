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
              Hello! I'm Yolanda Matiwane, an aspiring developer with a passion for creating and problem-solving. Originally from Langa, I graduated from high school in 2018 and have since embarked on an exciting journey into the world of coding.
              Since my introduction to coding in 2020 through visual Python in a physics class, I've been captivated by the process of turning code into tangible creations. This initial experience sparked my fascination with understanding how things work and the thrill of seeing ideas materialize into visualizations or functional applications. While I'm still in the early stages of my coding career, I'm eager to expand my skills and knowledge. I enjoy tackling challenges and am constantly exploring new concepts to enhance my understanding of programming. I thrive on learning new things and applying my creativity to problem-solving. Beyond coding, I indulge in reading, watching movies, and gaming, activities that fuel my imagination and inspire my work. My goal is to continue growing as a developer, translating my ideas into impactful projects. I'm excited about the possibilities that coding offers and look forward to contributing to innovative solutions in the tech industry.
            </div>
          </div>
          <div class="col-sm-4 lg-12">
            <img src="https://yolandamatiwane.github.io/vueProjectImages/20240422_122336.jpg">
          </div>
          <br>
          <h3><span class="cursor">></span>Skills</h3>
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
