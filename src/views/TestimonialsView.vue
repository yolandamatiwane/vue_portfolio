<template>
    <h1>Testimonials:</h1>
    <div>
        <div data-aos="zoom-in" data-aos-duration="1500" class="card" v-for="testimonial in pageTestimonialsData" :key="testimonial.name">
            <div class="container text-center">
                <div class="row">
                    <span></span>
                    <div class="col-lg-3 col-sm-12" >
                        <img :src="testimonial.image">
                    </div>
                    <div class="col-lg-9 col-sm-12" id="comment">
                        <h3 class="card-title">{{testimonial.name}}</h3>
                        <h5>
                            {{ testimonial.message}}

                        </h5>
                    </div>
                </div>
            </div>
                
        </div>
    </div>
</template>
<script>
export default {
    computed:{
        pageTestimonialsData(){
            return this.$store.state.testimonials
        }
    }

}
</script>
<style scoped>
    h1{
    margin-top: 50px;
    font-family:"Bangers";
    font-size: 100px;
    color: #bb7aad;
    text-shadow: 2px 2px 4px #000000;
    }
    h3{
        margin-top:30px;
        /* color:white; */
        font-weight:900;
    }
    h5{
        margin-left:25px;
        width: 900px;
        margin-top:50px;
        /* color:white; */
        font-weight:900;
    }
    .card{
        height:auto;
        /* background-image:url('https://yolandamatiwane.github.io/vueProjectImages/QL2EBM.jpg'); */
        background-color:rgb(204, 192, 255);
        width:90%;

        border:none;
        margin-top:100px;
        margin-bottom:40px;
        margin-left:90px;
    }
    img{
        width:300px;
        height:400px;
        border-radius:20%;
        border:5px solid pink;
        box-shadow: 10px 10px 5px;
        
    }
    #comment{
        background-image:url('https://yolandamatiwane.github.io/vueProjectImages/168f0adf88b26e7c025e3db7b93607a2.png');
        background-size:cover;
        box-shadow: 10px 10px 5px;
        border-radius:10px ;
    }
    @media only screen and (max-width:1000px) {
        h1{
            margin: 0;
            font-size: 60px;
        }
        .card{
            /* margin-top: 30px; */
            width: 100%;
            height: auto;
            margin:0;
            font-size: 20px;
            justify-content: center;
            margin-bottom: 40px;
        }
        #comment{
            margin-top: 10px;
            margin-left: 10px;
            background-image: none;
            background-color: rgba(153, 116, 150, 0.3);
            width: 95%;
            padding: 20px;
        }
        h5{
            width: fit-content;
            
        }
        img{
            width: 70%;
            margin: 0;
            border: 4px solid rgba(222, 74, 209, 0.3);
        }
    }
   
</style>