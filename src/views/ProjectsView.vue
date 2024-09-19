<template>
    <h1>Projects:</h1>
    <select class="btn btn-outline-dark" v-model="selectedCategory">
      <option value="">
        All categories
      </option>
      <option value="javascript">
        Javascript
      </option>
      <option value="bootstrap">
        Bootstrap
      </option>
      
    </select>
    <div id="about">
      <div class="card" v-for="project in filterProjects" :key="project.name">
        <div >
          <h3>
            ><span class="typing-effect">{{ project.name }}</span><span class="cursor">_</span>
          </h3>
          <img data-aos="zoom-in" data-aos-duration="1500" v-if="project.visuals.type === 'image'" :src="project.visuals.url">
          <video v-else :src="project.visuals.url" type="video/mp4" controls>
          </video>
          <p>{{ project.description }}</p>
          <div id="bnts">
            <a :href="project.gitHub" target="_blank" class="btn btn-outline-custom">GitHub</a>
            <a :href="project.vercel" target="_blank" class="btn btn-outline-custom">Live Demo</a>
          </div>
        </div>
        
          
      </div>
    </div>
      
  </template>
  <script>
  // import SpinnerComp from '/src/components/SpinnerComp.vue'
  export default {
      // components:{
      //   SpinnerComp
      // },
      data(){
        return {
          selectedCategory:''
        }
  
      },
      computed:{
        filterProjects(){
          if(this.selectedCategory === '') {
            return this.$store.state.projects
          } else{
            return this.$store.state.projects.filter(project => project.category === this.selectedCategory)
          }
        }
        
      },
      methods: {
        projectLoaded(project) {
          return project.loaded === true
        }
      }
      
  }
  </script>
  <style scoped>
    h1{
      margin-top: 20px;
      font-family:"Bangers";
      font-size: 50px;
      color: #bb7aad;
      text-shadow: 2px 2px 4px #000000;
    }
    h3{
      color:white;
      font-weight: 900;
      font-size:30px;
      margin-top:80px;
      display: flex;
      align-items: center;
    }
    .typing-effect{
      border-right: 2px solid white;
      white-space: nowrap;
      overflow: hidden;
      animation: typing 2s steps(20,end);
    }
    .cursor{
      font-size:30px;
      animation: blink-caret 0.75s step-end infinite;
    }
    img{
      width:80%;
      height:250px;
      border-radius: 10px;
      box-shadow: 10px 10px 5px #670652;
      margin-bottom: 20px;
    }
    img:hover{
      box-shadow: 10px 10px 5px rgb(253, 194, 243);
    }
    #about {
      display: flex;
      justify-content: center;
      flex-wrap: wrap;
      text-align:start;
    }
    h5{
      color:white;
      font-weight: 800;
    }
    p{
      width: 100%;
    }
    .card{
      background-color: rgba(128, 0, 128, 0.0);
      width:40%;
      
      margin-left:70px;
      margin-top:10px;
      margin-bottom:30px;
      border: none;
      font-weight:900;
    }

    .btn-outline-custom, .btn-outline-dark{
      margin-left:20px;
      height:60px;
    }
    .btn-outline-dark{
      padding: auto;
      font-family: "Bangers";
      font-size: 20px;
      box-shadow: 2px 2px 4px;
      width:15%;
      /* margin-left:100px; */
    }
    .btn-outline-custom{
      padding: auto;
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
    #btns{
      display: inline;
      padding: 100px;
      width:100%;
      justify-content: space-between;
      
    }
    @keyframes typing {
      from { width: 0; }
      to { width: 100%; }
    }

    @keyframes blink-caret {
      from, to { border-color: transparent; }
      50% { border-color: white; }
    }
    @media only screen and (max-width:768px){
      h1{
        font-size: 40px;
      }
      .btn-outline-dark , .btn-outline-custom{
        width:80%;
        font-size:30px;
      }
      h3{
        font-size: 40px;
      }
      #about{
        display: grid;
        grid-template-columns: repeat(1,1fr);
      }

      .card{
        width: 90%;
        margin: auto;
      }
      @media only screen and (max-width:480px) {
        .btn-outline-dark{
          font-size: 10px;
        }
        .btn-outline-custom{
          font-size: 14px;
          height: 40px;
          margin-bottom: 5%;
          
        }
        
        h3{
          font-size: 20px;
        }
        p{
          font-size: 15px;
        }
        img{
          width: 100%;
        }
      }
    }
  </style>