<template>
    <div id="resumeMainDiv">
        <a href="https://docs.google.com/document/d/13-QKdcSl-EjYXoaCUtDCAho8w_uptShLVTAaEfVjGUw/edit?usp=sharing" target="_blank"><button class="btn btn-outline-dark"> My CV</button></a>
        <div class="card">
            <h2><img src="https://yolandamatiwane.github.io/vueProjectImages/animatedIcons/telecommuting-unscreen.gif" id="img"/></h2>
            <h3>Work Experience:</h3>
                <div class="flex-container2">
                    <div v-for="work in workExpData" :key="work.description" id="eduDivs">
                        <!-- <img :src="work.img" id="eduImg"/> -->
                        <div id="info">
                            <h4><span>></span>  {{ work.year }}</h4>
                            <h5><label>Place of Employment:</label> {{ work.placeOfWork }}</h5>
                            <h5><label></label> {{ work.description }}</h5>
                        </div>
                </div>
            </div>
        </div>
        <div class="card">
            <h2><img src="https://yolandamatiwane.github.io/vueProjectImages/animatedIcons/validation-unscreen.gif" id="img" /></h2>
            <h3>Badges: </h3>
           <div class="flex-container" id="badgeDivs">
                <div v-for="badge in badgesData" :key="badge.description" >
                    <img :src="badge.img" id="badgeImg"/>
                </div> 
           </div> 
        </div>
        <div class="card">
            <h2><img src="https://yolandamatiwane.github.io/vueProjectImages/animatedIcons/education-1--unscreen.gif" id="img" /></h2>
            <h3>Education: </h3>
           <div class="flex-container mt-2">
                <div v-for="edu in educationData" :key="edu.description" id="eduDivs">
                    <!-- <img :src="edu.img" id="eduImg"/> -->
                    <div>
                        <h4><span>></span> {{ edu.year }}</h4>
                        <h5><label>Institution:</label>  {{ edu.institution }}</h5>
                        <h5>{{edu.description}}</h5>
                    </div>

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
        badgesData(){
            return this.$store.state.badges
        }
    }
}
</script>
<style scoped>
    #resumeMainDiv{
        margin-top: 90px;
    }
    #badgeImg{
        width: 120px;
        animation: bounce 2s infinite ease-in-out;
    }
    /* #info{
        background-color: #bb7aad;
        border-radius: 10px;
        padding: 55px ;
    } */
    /* #badgeDivs {
        display: flex;
        flex-wrap: wrap;
        justify-content: center; 
        gap: 20px;
    } */
    @keyframes bounce {
        0%, 20%, 50%, 80%, 100% {
            transform: translateY(0);
        }
        40% {
            transform: translateY(-20px);
        }
        60% {
            transform: translateY(-10px);
        }
    }
    #eduImg{
        width: 100px;
        height: 70px;
        border: 5px solid #bb7aad;
        border-radius: 50%;
    }
    #img{
        width: 60px;
    }
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
        /* background-color: #bb7aad; */
        /* margin-left: 150px; */
        border-radius: 10px;
        padding: 55px ;
    }
    #eduDivs{
        background-color: #bb7aad;
        width: 30%;
        border-radius: 10px;
        padding: 55px ;
        margin-bottom: 25px;
        box-shadow: 0 15px 25px #670652;
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
            margin-top: 15px;
        }
        #badgeDivs {
            display: grid;
            grid-template-columns: repeat(3, 1fr);
            gap: 20px;
            justify-content: center; 
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
            text-align: center;
        }
        /* #badgeDivs {
            display: grid;
            grid-template-columns: repeat(3, 1fr);
            gap: 20px;
            justify-content: center; 
        } */

    }
    @media(max-width:450px){
        #eduDivs, #workDiv{
            width: 100%;
        }
        .btn-outline-dark{
            width: 40%;
        }
        #badgeDivs {
            grid-template-columns: repeat(2, 1fr); 
        }
    }
</style>