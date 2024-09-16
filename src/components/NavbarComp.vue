<template>
  <nav class="navbar navbar-expand-lg">   
    <div id="nav" class="container-fluid">
            <a class="navbar-brand" href="#">
              <!-- <img class="logo" src="https://yolandamatiwane.github.io/vueProjectImages/icons/Beige%20Minimal%20Personal%20Make%20Up%20Artist%20Logo.png" id="logo"> -->
          </a>
            <button class="navbar-toggler" type="button" data-bs-toggle="collapse" data-bs-target="#navbarNav" aria-controls="navbarNav" aria-expanded="false" aria-label="Toggle navigation">
              <span class="navbar-toggler-icon" ></span>
            </button>
            <div class="collapse navbar-collapse justify-content-end" id="navbarNav">
              <ul class="navbar-nav " ms-auto >
                <li class="nav-item">
                  <router-link to="/" @mousemove="show('Home')" @mouseleave="hide()">
                    <span class="nav-label" id="media">Home</span>
                    <!-- <i class="bi bi-house-door-fill"></i> -->
                      <img src="https://yolandamatiwane.github.io/vueProjectImages/icons/home%20(1).png">
                      <Transition name="fade" mode="out-in">
                        <span v-if="displayLabel && label==='Home'" class="nav-label">Home</span>
                      </Transition>
                  </router-link>
                </li>
                <li class="nav-item">
                  <router-link to="/about" @mousemove="show('About')" @mouseleave="hide()">
                      <img src="https://yolandamatiwane.github.io/vueProjectImages/icons/technology.png">
                    <Transition name="fade" mode="out-in">
                      <span v-if="displayLabel && label==='About'" class="nav-label">About</span>
                    </Transition>
                    <span class="nav-label" id="media">About</span>
                  </router-link>
                </li>
                <li class="nav-item">
                  <router-link to="/resume" @mousemove="show('Resume')" @mouseleave="hide()"> 
                    <img src="https://yolandamatiwane.github.io/vueProjectImages/icons/profile.png">
                    <Transition name="fade" mode="out-in">
                      <span v-if="displayLabel && label==='Resume'" class="nav-label">Education</span>
                    </Transition>
                    <span class="nav-label" id="media">Resume</span>
                  </router-link>
                </li>
                <li class="nav-item">
                  <router-link to="/projects" @mousemove="show('Projects')" @mouseleave="hide()"> 
                    <img src="https://yolandamatiwane.github.io/vueProjectImages/icons/idea.png">
                    <Transition name="fade" mode="out-in">
                      <span v-if="displayLabel && label==='Projects'" class="nav-label">Projects</span>
                    </Transition>
                    <span class="nav-label" id="media">Projects</span>
                  </router-link>
                </li>
                <!-- <li class="nav-item">
                  <router-link to="/testimonials" @mousemove="show('Testimonials')" @mouseleave="hide()"> 
                    <img src="https://yolandamatiwane.github.io/vueProjectImages/icons/testimonial.png">
                    <Transition name="fade" mode="out-in">
                      <span v-if="displayLabel && label==='Testimonials'" class="nav-label">Testimonials</span>
                    </Transition>
                    <span class="nav-label" id="media">Testimonials</span>
                  </router-link>
                </li> -->
                <li class="nav-item">
                  <router-link to="/contacts" @mousemove="show('Contacts')" @mouseleave="hide()"> 
                    <img src="https://yolandamatiwane.github.io/vueProjectImages/icons/contact-me.png">
                    <Transition name="fade" mode="out-in">
                      <span v-if="displayLabel && label==='Contacts'" class="nav-label">Contacts</span>
                    </Transition>
                    <span class="nav-label" id="media">Contacts</span>
                  </router-link>
                </li>           
              </ul>
            </div>
          </div>
  </nav>
</template>
<script>


export default {
data() {
  return {
    displayLabel:false,
    label: ''
  }
},
methods:{
  show(name){
    this.displayLabel = true;
    this.label = name;
  },
  hide(){
    this.displayLabel = false;
  }
}
}
</script>
<style scoped>

nav{
  background-color: rgba(137, 43, 226, 0);
  display: flex;
  align-items: center;
}
#logo{
  width: 200px;
}
.nav-label{
  text-shadow: 2px 2px 4px white;
}  
img{
  width: 40px;
  height: 40px;
}  
.fade-enter-active,
.fade-leave-active {
  transition: opacity 0.8s ease;
}  
.fade-enter-from,
.fade-leave-to {
  opacity: 0;
}
.logo{
  width: 100px;
  height:40px;
}
#media{
  display: none;
}
@media only screen and (max-width:970px){
  nav{
    width: 100%;
  }
  .nav-item img{
    display: none;
    width: 30px;
    height: 30px;
  }
  .nav-item .nav-label{
    display: none;
  }
  .fade-enter-active,
  .fade-leave-active {
    transition: none;
  }

  #media{
    display: inline-block;
    font-size: 16px;
  }
}
@media only screen (min-width:970) {
  
}
</style>