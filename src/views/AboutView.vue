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
              <p>Hello! I'm Yolanda Matiwane,23, an aspiring developer from Langa with a passion for coding and problem-solving. </p>
              <p>I discovered my love for programming in 2020 during a physics class where I learned visual Python. Since then, I've been captivated by the process of transforming ideas into functional applications. I enjoy tackling challenges and constantly seek to expand my skills.</p>
              <p>Outside of coding, I love reading, watching movies, and gaming, which fuel my creativity.</p>
              My goal is to grow as a developer and contribute to innovative solutions in the tech industry.
            </h5>
          </div>
          <br>
          <div class="row" id="skillDiv">
            <h3>Skills:</h3>
                <div class="col-sm-6 col-12" id="skill"> 
                    <h4>Coding Skills</h4>
                    <div v-for="skill in skillsData" :key="skill.name" >
                        <h5>
                            <span>></span> {{ skill.name }}
                        </h5>  
                    </div>
                </div>
                <div class="col-sm-6 col-12" id="skill">
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
    border-radius:50%;
    /* margin-left:600px; */
    box-shadow: 4px 4px 2px black;
    /* border: 4px solid rgba(153, 116, 150, 0.3); */
  }
  .col-sm-8 {
    /* box-shadow: 4px 4px 2px white; */
    background-color: rgba(255, 255, 255, 0);
    border-radius: 10px;
    align-items: center;
    /* color: white; */
  }
  .card-text{
    /* align-items: center; */
    /* justify-content: center; */
    /* text-shadow: 4px 4px 2 px white; */
    margin-top: 10px;
    /* color: white; */
  }
  #mainAboutDiv {
    font-family:"Bangers";
    justify-content: center;
    /* margin-bottom: 50px; */
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
    /* width:35%; */
    /* margin-left: 130px; */
  }
  #skillDiv{
    margin-top: 30px;
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
  @media(max-width:800px){
    img{
      width: fit-content;
      height: 200px;
      margin: auto;

    }
    .card{
      width: 100%;
    }
  }
  @media(max-width:575px){
    #skill{
      text-align: center;
      margin-top: 20px;
    }
  }
</style>
