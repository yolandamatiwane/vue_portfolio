<template>
    <h1>Projects:</h1>
    <!-- <select class="btn btn-outline-dark" v-model="selectedCategory">
      <option value="">
        All categories
      </option>
      <option value="javascript">
        Javascript
      </option>
      <option value="bootstrap">
        Bootstrap
      </option>
      
    </select> -->
    <div id="about">
      <div class="card" v-for="(project,index) in filterProjects" :key="project.name">
        <div class="card-content">
          <h3>
            ><span class="typing-effect">{{ typedText[index] }}</span><span class="cursor" :class="{ blinking: isBlinking }">_</span>
          </h3>
          <div data-aos="zoom-out" data-aos-duration="1500">
            <img v-if="project.visuals.type === 'image'" :src="project.visuals.url">
            <video v-else :src="project.visuals.url" type="video/mp4" controls>
            </video>
          </div>
          <p v-if="project.showDescription">{{ project.description }}</p>

          <div id="bnts" class="align-items-center">
            <button @click="toggleDescription(index)" class="btn btn-outline-custom" data-bs-toggle="tooltip" data-bs-placement="bottom" data-bs-title="project description">
                <i class="bi bi-info-circle-fill"></i>
            </button>
            <a :href="project.gitHub" target="_blank" class="btn btn-outline-custom mx-1"
            data-bs-toggle="tooltip" data-bs-placement="top"
              data-bs-custom-class="custom-tooltip"
              data-bs-title="project description"><i class="bi bi-github"></i></a>
            <a :href="project.vercel" target="_blank" class="btn btn-outline-custom mx-1"><i class="bi bi-rocket-takeoff-fill"></i></a>
          </div>
        </div>
      </div>
    </div>
      
  </template>
  <script>
  // import SpinnerComp from '/src/components/SpinnerComp.vue'
  // import 'bootstrap';
  export default {
      // components:{
      //   SpinnerComp
      // },
      data(){
        return {
          selectedCategory:'',
          typedText:[],
          typingSpeed:100,
          isBlinking:true,
          projectVisibility: []
        }
  
      },
      computed:{
        filterProjects() {
          if (this.selectedCategory === '') {
            return this.$store.state.projects.map((project, index) => ({
              ...project,
              showDescription: this.projectVisibility[index] || false, // Assign visibility state
            }));
          } else {
            return this.$store.state.projects.filter(project => project.category === this.selectedCategory)
              .map((project, index) => ({
                ...project,
                showDescription: this.projectVisibility[index] || false,
              }));
          }
        }
      },
      methods: {
        toggleDescription(index) {
          this.projectVisibility[index]= !this.projectVisibility[index]
        },
        projectLoaded(project) {
          return project.loaded === true
        },
        startTypingEffect(index) {
          const projectName = this.filterProjects[index]?.name || '';
          this.typedText[index] =''
          let charIndex = 0;

          const typingInterval = setInterval(() => {
            if (charIndex < projectName.length) {
              this.typedText[index] += projectName.charAt(charIndex);
              charIndex++;
            } else {
              clearInterval(typingInterval);
            }
          }, this.typingSpeed);
        },
        blinkCursor() {
          setInterval(() => {
            this.isBlinking = !this.isBlinking;
          }, 500);
        },
      },
      mounted() {
        this.blinkCursor();
        this.filterProjects.forEach((_, index) => {
          this.startTypingEffect(index);
          this.projectVisibility[index] = false; // Initialize visibility state
        })
        // const tooltipTriggerList = [].slice.call(document.querySelectorAll('[data-bs-toggle="tooltip"]'));
        //   tooltipTriggerList.forEach(tooltipTriggerEl => {
        //     new bootstrap.Tooltip(tooltipTriggerEl);
        //   });
      }
    };
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
      font-size:25px;
      margin-top:80px;
      display: flex;
      align-items: center;
    }
    .typing-effect{
      display:inline-block;
    }
    .cursor{
      font-size:30px;
    }
    .blinking {
      opacity: 1;
      animation: blink-caret 0.75s step-end infinite;
    }
    img{
      width:95%;
      height:250px;
      border-radius: 10px;
      /* box-shadow: 10px 10px 5px #670652; */
      box-shadow: 0 15px 25px #670652;
      margin-bottom: 20px;
      transition: transform 0.5s ease, box-shadow 0.5s ease;
      transform: translateY(-5px);
    }
    img:hover{
      box-shadow: 0 5px 15px rgba(0, 0, 0, 0.2);
      /* box-shadow: 0px 10px 20px rgba(0, 0, 0, 0.5);  */
      /* transform: scale(1.05);  */
      /* opacity: 0.9; */
      transform: translateY(0);
      
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
      height: 650px;
      margin-left:70px;
      margin-bottom:30px;
      border: none;
      font-weight:900;
      display:flex;
      flex-direction:column;
    }
    #bnts {
      display: flex;
      justify-content: center; 
      align-items: center;
      margin-top: 20px; 

      margin: auto;
    }

    .btn-outline-custom, .btn-outline-dark{
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
      display: flex;
      justify-content: center;
      align-items: center;
      padding: auto;
      font-family:"Bangers";
      font-size: 20px;
      color: white;
      background-color: #670652;
      box-shadow: 2px 2px 4px;
      width: 200px ;
      transition: transform 0.5s ease, background-color 0.5s ease, color 0.5s ease, border-color 0.5s ease;
    }
    .btn-outline-custom:hover{
      transform: scale(1.1);
      background-color: white;
      color: #670652;
    }

    @keyframes typing {
      from { width: 0; }
      to { width: 100%; }
    }

    @keyframes blink-caret {
      from, to { opacity: 0; }
      50% { opacity: 1; }
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