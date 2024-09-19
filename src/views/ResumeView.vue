<template>
    <div id="resumeMainDiv">
        <a href="https://1drv.ms/w/c/c603b707ec55c120/ESDBVewHtwMggMaLBAAAAAABbM-MPM5RWTgSVZdrBlTG3Q" target="_blank"><button class="btn btn-outline-dark"> My CV</button></a>
        <div class="card">
            <h3>Work Experience:</h3>
                <div class="flex-container">
                    <div v-for="work in workExpData" :key="work.description" id="workDiv">
                    <h4><span>></span>  {{ work.year }}</h4>
                    <h5><label>Place of Employment:</label> {{ work.placeOfWork }}</h5>
                    <h5><label>Role:</label>{{ work.description }}</h5>
                    <h6>Reference:</h6>
                    <h5><label>Name:</label> {{ work.contact.name }}</h5>
                    <h5 v-if="work.contact.position"><label>Position:</label> {{ work.contact.position }}</h5>
                    <h5><label>Email:</label> {{ work.contact.email }}</h5>

                </div>
            </div>
        </div>
        <div class="card">
            <h3>Education:</h3>
           <div class="flex-container">
                <div v-for="edu in educationData" :key="edu.description" id="eduDivs">
                    
                    <h4><span>></span> {{ edu.year }}</h4>
                    <h5><label>Institution:</label>  {{ edu.institution }}</h5>
                    <h5>{{edu.description}}</h5>

                </div> 
           </div> 
        </div>
    </div>
</template>
<script>

export default {

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
    label,span{
        color:#bb7aad;
        /* text-shadow: 2px 2px 4px #000000; */
    }
    .card h3, span{
        text-align: center;
        text-shadow: 2px 2px 4px #ffffff;

    }
    #eduDivs, #workDiv{
        /* box-shadow: 4px 4px 2px white; */
        text-align: start;
        width: 35%;
        margin-bottom: 10px;
        /* background-color: #2c3e50; come back */
        margin-left: 170px;
        border-radius: 10px;

    }
   .card {
        background-color: rgb(204, 192, 255);
        /* background-color: #2c3e50; */
        font-family: "Bangers";
        margin-bottom: 20px;
        margin-top: 40px;
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
    .flex-container {
        /* align-items: start; */
        justify-content: center;
        display: flex;
        flex-wrap: wrap;
        /* justify-content: space-between; */
    }
    @media(max-width:1100px){
        #eduDivs, #workDiv{
            margin-left:0px;
        }
    }
    @media(max-width:770px){
        .flex-container{
            flex-direction: column;
            align-items: center;
            justify-content: center;
        }
        /* #eduDivs, #workDiv{
            width: 100%;
            align-items: center;
            margin: auto;
        } */
    }
</style>