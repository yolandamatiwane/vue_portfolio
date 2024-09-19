<template>
  <nav class="navbar navbar-expand-lg">   
    <div id="nav" class="container-fluid">
            <a class="navbar-brand" href="#">
                  Yolanda<span> M</span>
            </a>
            <button class="navbar-toggler" type="button" data-bs-toggle="collapse" data-bs-target="#navbarNav" aria-controls="navbarNav" aria-expanded="false" aria-label="Toggle navigation">
              <span class="navbar-toggler-icon" ></span>
            </button>
            <div class="collapse navbar-collapse justify-content-end" id="navbarNav">
              <ul class="navbar-nav " ms-auto >
                <li class="nav-item">
                  <router-link to="/" @mousemove="show('Home')" @mouseleave="hide()">
                    <div class="nav-content">
                      <span class="nav-label" id="media">Home</span>
                      <i class="bi bi-house-door-fill"></i>
                      <!-- <img src="https://yolandamatiwane.github.io/vueProjectImages/icons/home%20(1).png"> -->
                      <Transition name="fade" mode="out-in">
                        <span v-if="displayLabel && label==='Home'" class="nav-label">Home</span>
                      </Transition>
                    </div>
                  </router-link>
                </li>
                <li class="nav-item">
                  <router-link to="/about" @mousemove="show('About')" @mouseleave="hide()">
                    <div class="nav-content">
                     <!-- <i class="bi bi-lightbulb"></i> -->
                      <i class="bi bi-info-circle-fill"></i>
                        <!-- <img src="https://yolandamatiwane.github.io/vueProjectImages/icons/technology.png"> -->
                      <Transition name="fade" mode="out-in">
                        <span v-if="displayLabel && label==='About'" class="nav-label">About</span>
                      </Transition>
                      <span class="nav-label" id="media">About</span>
                    </div>
                  </router-link>
                </li>
                <li class="nav-item">
                  <router-link to="/resume" @mousemove="show('Resume')" @mouseleave="hide()">
                    <div class="nav-content">
                      <!-- <i class="bi bi-file-earmark-person"></i>  -->
                      <i class="bi bi-book-fill"></i>
                      <!-- <img src="https://yolandamatiwane.github.io/vueProjectImages/icons/profile.png"> -->
                      <Transition name="fade" mode="out-in">
                        <span v-if="displayLabel && label==='Resume'" class="nav-label">Education & Experience</span>
                      </Transition>
                      <span class="nav-label" id="media">Education</span>
                    </div>
                  </router-link>
                </li>
                <li class="nav-item">
                  <router-link to="/projects" @mousemove="show('Projects')" @mouseleave="hide()"> 
                    <div class="nav-content">
                      <!-- <i class="bi bi-gear"></i> -->
                      <i class="bi bi-person-workspace"></i>
                      <!-- <img src="https://yolandamatiwane.github.io/vueProjectImages/icons/idea.png"> -->
                      <Transition name="fade" mode="out-in">
                        <span v-if="displayLabel && label==='Projects'" class="nav-label">Projects</span>
                      </Transition>
                      <span class="nav-label" id="media">Projects</span>
                    </div>
                  </router-link>
                </li>
                <li class="nav-item">
                  <router-link to="/contacts" @mousemove="show('Contact')" @mouseleave="hide()"> 
                    <div class="nav-content">
                      <i class="bi bi-envelope"></i>
                      <!-- <img src="https://yolandamatiwane.github.io/vueProjectImages/icons/contact-me.png"> -->
                      <Transition name="fade" mode="out-in">
                        <span v-if="displayLabel && label==='Contact'" class="nav-label">Contact</span>
                      </Transition>
                      <span class="nav-label" id="media">Contact</span>
                    </div>
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
  .navbar-brand{
    font-family: "Bangers";
  }
  nav{
    background-color: rgba(137, 43, 226, 0);
    display: flex;
    align-items: center;
  }
  nav li{
    padding-right: 60px;
    padding-bottom: 0px;
  }
  nav a {
    font-weight: bold;
    color: rgb(2, 2, 94);
    text-decoration: none;
    font-weight: 900;
  }
  .nav-item{
    transition:2s;
  }
  nav a.router-link-exact-active {
    color: rgb(160, 115, 156);

  }
  .bi {
    font-size: 30px;
    border-color: white ;
  }

  .nav-label {
  text-shadow: 2px 2px 4px white;
  position: absolute;
  top: 100%;
  left: 50%;
  transform: translateX(-50%);
  z-index: 10;
  transition: opacity 0.3s ease, visibility 0.3s ease; /* Smooth fade-in and visibility transition */
  }  

  .fade-enter-active,
  .fade-leave-active {
    transition: opacity 0.8s ease;
  }  
  .fade-enter-from,
  .fade-leave-to {
    opacity: 0;
  }

  #media{
    display: none;
  }
  .nav-content {
  display: flex;
  flex-direction: column;
  align-items: center;
 }

 /* Existing styles */
 @keyframes fall {
  from {
    opacity: 0; /* Start hidden */
    transform: translateY(-20px); /* Start from above */
  }
  to {
    opacity: 1; /* End fully visible */
    transform: translateY(0); /* End at final position */
  }
}

.nav-content {
  animation: fall 1s ease-out forwards;
  opacity: 0; /* Start hidden */
  transform: translateY(-20px); /* Start from above */
}

.nav-item:nth-child(1) .nav-content {
  animation-delay: 0.1s; /* Stagger the animation */
}

.nav-item:nth-child(2) .nav-content {
  animation-delay: 0.2s;
}

.nav-item:nth-child(3) .nav-content {
  animation-delay: 0.3s;
}

.nav-item:nth-child(4) .nav-content {
  animation-delay: 0.4s;
}

.nav-item:nth-child(5) .nav-content {
  animation-delay: 0.5s;
}

.navbar-nav .nav-item {
  margin-bottom: 1rem; /* Adjust as needed */
}

@media (max-width: 770px) {
  /* .bi {
    display: none;
  } */
  .nav-label {
    display: block;
  }
  /* .nav-content {
    flex-direction: row; 
    align-items: center;
    justify-content: center;
  } */
}
</style>