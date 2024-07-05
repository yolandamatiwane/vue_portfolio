<template>
    <div id="resumeMainDiv">
        <h1>Resume:</h1>
        <spinner-comp/>
        <a href="https://1drv.ms/w/c/c603b707ec55c120/ESDBVewHtwMggMaLBAAAAAABbM-MPM5RWTgSVZdrBlTG3Q" target="_blank"><button class="btn btn-outline-dark"> My CV</button></a>
        <div class="card">
            <img src="https://yolandamatiwane.github.io/vueProjectImages/resume/Animation%20-%201720060177546.gif">
            <h3>Education:</h3>
           <div class="flex-container">
                <div v-for="edu in educationData" :key="edu.description" id="eduDivs">
                    
                    <h4><span>></span> {{ edu.year }}</h4>
                    <h5>Institution:  {{ edu.institution }}</h5>
                    <h5>{{edu.description}}</h5>

                </div> 
           </div> 
        </div>
        <div class="card">
            <h5>Work Experience:</h5>
            <img src="https://yolandamatiwane.github.io/vueProjectImages/resume/Animation%20-%201720014506045.gif">
                <div>
                    <div v-for="work in workExpData" :key="work.description">
                    <h4><span>></span>  {{ work.year }}</h4>
                    <h5><label>Place of Employment:</label> {{ work.placeOfWork }}</h5>
                    <h5>{{ work.description }}</h5>
                    <h6>Reference:</h6>
                    <h5><label>Name:</label> {{ work.contact.name }}</h5>
                    <h5><label>Position:</label> {{ work.contact.position }}</h5>
                    <h5><label>Email:</label> {{ work.contact.email }}</h5>

                </div>
            </div>
        </div>
        <div class="card">
            <h5>Skills:</h5>
            <img src="https://yolandamatiwane.github.io/vueProjectImages/resume/Animation%20-%201720014157565.gif">
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
</template>
<script>
import SpinnerComp from '@/components/SpinnerComp.vue';
export default {
    components:{
        SpinnerComp
    },
    computed:{
        educationData(){
            return this.$store.state.education
        },
        workExpData(){
            return this.$store.state.workExperience
        },
        skillsData(){
            return this.$store.state.skills
        }
    }
}
</script>
<style scoped>
    img{
        width:300px;
        height:200px;
        margin-left:700px;
    }
    .card{
        background-color:rgb(204, 192, 255);
        font-family:"Bangers";
        margin-bottom: 20px;
        
    }
    #resumeMainDiv {
        margin-top: 60px;


    }
    h1{
        font-family:"Bangers";
        font-size: 100px;
        color: #bb7aad;
        text-shadow: 2px 2px 4px #000000;
    }
    label{
        color:white;
    }
    #eduDivs{
        box-shadow: 4px 4px 2px white;
        width: 30%;
        margin-bottom: 10px;
    }
   .card {
        background-color: rgb(204, 192, 255);
        font-family: "Bangers";
        margin-bottom: 20px;
        display: flex;
        border: none;

    }
    .btn-outline-dark{
      padding: auto;
      font-family: "Bangers";
      font-size: 20px;
      box-shadow: 2px 2px 4px;
      width:15%;
      /* margin-left:100px; */
    }
    #resumeMainDiv {
        margin-top: 60px;
    }
    h1 {
        font-family: "Bangers";
        font-size: 100px;
        color: #bb7aad;
        text-shadow: 2px 2px 4px #000000;
    }
    label {
        color: white;
    }
    .flex-container {
        display: flex;
        flex-wrap: wrap;
        justify-content: space-between;
    }
    #icons{
        width: 40px;
    }
    #skillDiv div h5{
    text-align: start;  
    }
    #skillDiv{
        display: flex;
        flex-wrap: wrap;
        justify-content: space-evenly;
        margin-bottom: 20px
    }
    @media only screen and (max-width: 1000px){
        img {
            width: 30%; 
            height: auto; 
            margin-left: 350px;
        }
    }
    @media only screen and (max-width: 768px) {
        img {
            width: 70%; 
            height: auto; 
            margin-left: 0; 
            margin: 0 40px;
        }
        h1{
            font-size: 50px;
        }
        .flex-container{
            display: grid;
            grid-template-columns: repeat(1,1fr);
        }
        #eduDivs{
            width: 90%;
        }
        .btn-outline-dark{
        width:60%;
        font-size:20px;
      }
    }
    @media only screen and (max-width: 480px) {
        #skillDiv{
            text-align: start;
            width: 100%;
        }
        .btn-outline-dark{
          font-size: 10px;
        }

    }
</style>