<template>
    <div id="resumeMainDiv">
        <a href="https://1drv.ms/w/c/c603b707ec55c120/ESDBVewHtwMggMaLBAAAAAABbM-MPM5RWTgSVZdrBlTG3Q" target="_blank"><button class="btn btn-outline-dark"> My CV</button></a>
        <div class="card">
            <h3>Work Experience:</h3>
                <div class="flex-container2">
                    <div v-for="work in workExpData" :key="work.description" id="workDiv">
                    <h4><span>></span>  {{ work.year }}</h4>
                    <h5><label>Place of Employment:</label> {{ work.placeOfWork }}</h5>
                    <h5><label>Role:</label> {{ work.description }}</h5>
                    <!-- <h6>Reference:</h6>
                    <h5><label>Name:</label> {{ work.contact.name }}</h5>
                    <h5 v-if="work.contact.position"><label>Position:</label> {{ work.contact.position }}</h5>
                    <h5><label>Email:</label> {{ work.contact.email }}</h5> -->

                </div>
            </div>
        </div>
        <div class="card">
            <h3>Education:</h3>
           <div class="flex-container mt-2">
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
        color: rgb(2, 2, 94);
        text-shadow: 2px 2px 4px #ffffff;
    }
    .card h3, span{
        text-align: center;
        text-shadow: 2px 2px 4px #ffffff;

    }
    #workDiv{
        /* box-shadow: 4px 4px 2px white; */
        text-align: center;
        width: 35%;
        margin-top: 10px;
        margin-bottom: 20px;
        background-color: #bb7aad;
        /* margin-left: 150px; */
        border-radius: 10px;
        padding: 55px ;
    }
    #eduDivs{
        background-color: #bb7aad;
        /* width: 25%; */
        border-radius: 10px;
        padding: 55px ;
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
        display: flex;
        flex-wrap: wrap;
        justify-content: space-evenly;
    }
    .flex-container2{
        display: flex;
        flex-wrap: wrap;
        justify-content: space-evenly
    }
    @media(max-width:1150px){
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
        #eduDivs, #workDiv{
            margin-left:0px;
            width: 100%;
            /* align-items: center; */
            text-align: center;
            /* margin: auto; */
        }
    }
    @media(max-width:450px){
        #eduDivs, #workDiv{
            width: 100%;
        }
        .btn-outline-dark{
            width: 40%;
        }
    }
</style>