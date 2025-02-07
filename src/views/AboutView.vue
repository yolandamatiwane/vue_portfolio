<template>
  <div id="mainAboutDiv">  
    <h1>
      About Me:
    </h1> 
    <div class="card">
      <div class="container text-center">
        <div class="row" id="about">
          <div class="col-sm-4 lg-12" data-aos="fade-right" data-aos-duration="2000" data-aos-easing="ease-in-out">
            <img src="https://yolandamatiwane.github.io/vueProjectImages/20240422_122336.jpg">
          </div>
          <div class="col-sm-8 lg-12" data-aos="fade-left" data-aos-duration="2000" data-aos-easing="ease-in-out">
            <h5 class="card-text">
              <p>Hello! I'm Yolanda Matiwane, 23, an aspiring developer from Langa with a passion for coding and problem-solving.</p>
              
              <p>
                My journey into programming started in 2020 during a physics class when I was introduced to Visual Python—and I was instantly hooked! There was something thrilling about turning abstract concepts into functional applications, and I’ve been chasing that excitement ever since. I love tackling challenges, refining my skills, and continuously learning new things.
              </p>
              
              <p>
                As a Full-Stack Developer, I have a solid foundation in web development. I’ve worked with front-end and back-end technologies like Vue.js, Node.js, MySQL, and Python, and my background in Applied Mathematics sharpens my analytical thinking, helping me break down complex problems into structured solutions.
              </p>
              
              <p>
                I’m especially passionate about innovation, real-time data processing, and using technology to build impactful solutions. Whether working solo or collaborating with a team, I thrive in dynamic environments that push me to grow as a developer.
              </p>
              <p>Outside of coding, I’m naturally curious and love exploring new ideas. Reading, watching movies, and diving into different series fuel my creativity, allowing me to step into unknown worlds and expand my imagination. I also enjoy trying out new things, spending time at the beach, and making memories with friends and family.</p>
              <p>
                My goal? To keep learning, keep building, and contribute to game-changing solutions in the tech industry.
              </p>
              

            </h5>
          </div>
        </div>
          <br>
        <div class="row" id="skillDiv">
          <h3>Skills:</h3>
            <div class="col-sm-6 col-12" id="skill" data-aos="fade-up-right" data-aos-duration="2000" data-aos-easing="ease-in-out"> 
                    <h4>Coding Skills</h4>
                    <div v-for="skill in skillsData" :key="skill.name" >
                        <h5>
                            <span>></span> {{ skill.name }}
                        </h5>  
                    </div>
            </div>
            <div class="col-sm-6 col-12" id="skill" data-aos="fade-up-left" data-aos-duration="2000" data-aos-easing="ease-in-out">
                    <h4>Soft Skills</h4>
                    <h5>
                        <span>></span> Problem-Solving and Critical Thinking
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
                        <span>></span> Adaptability
                    </h5>
                    <h5>
                        <span>></span> Networking
                    </h5>
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
  #about{
    margin: auto;
  }
  .col-sm-4{
    display: flex;
    justify-content: center;
    align-content: center;

  }
  img{
    width:250px;
    height:250px;
    border-radius:50%;
    box-shadow: 0 15px 25px #670652;
  }
  .col-sm-8 {
    /* box-shadow: 4px 4px 2px white; */
    /* background-color: rgba(255, 255, 255, 0); */
    background-color: #bb7aad;
    border-radius: 10px;
    align-items: center;
    box-shadow: 0 15px 25px #670652;
    /* color: white; */
  }
  .card-text{
    margin-top: 10px;
  }
  #mainAboutDiv {
    font-family:"Bangers";
    justify-content: center;
  }
  h1,h3{
    /* font-size: 50px; */
    color: #bb7aad;
    text-shadow: 2px 2px 4px #000000;
  }
  .card{
    min-height: 100vh;
    margin:auto;
    padding:10px;
    background-color:rgb(204, 192, 255);
    width:90%;
    border:none;
    text-shadow: 2px 2px 4px rgb(163, 163, 163);
  }
  span{
    color: #a01684;
    font-size: 20px;
  }
  #skill{
    text-align: center;
    background-color: #bb7aad;
    border-radius: 10px;
    width:35%;
    /* margin-left: 100px; */
    box-shadow: 0 15px 25px #670652;
  }
  #skillDiv{
    margin-top: 30px;
    display: flex;
    flex-wrap: wrap;
    justify-content: space-evenly;
    margin: auto;
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
  @media(max-width:850px){
    img{
      width: 70%;
      height: 200px;
      /* margin: auto; */

    }
    .card{
      width: 100%;
    }
    #skill{
      width: 40%;
      /* margin-left: 40px; */
    }
  }
  @media(max-width:575px){
    #skill{
      width: 100%;
      text-align: center;
      margin-top: 20px;
      /* font-size: smaller; */
    }
    h5{
      font-size: smaller;
    }
    img{
      margin-bottom: 10px;
    }
  }
</style>
