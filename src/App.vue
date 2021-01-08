<template>
  <div class="container-fluid" id="overallDiv">
    <!-- <div class="nameDiv mt-10 text-center d-block mr-auto ml-auto"> -->
      
      <h2 id="name" class="text-center   text-white" v-for="data in datas" :key="data.name">{{data.name}}</h2>
    <!-- </div> -->
    
    <!-- <div class="rows"> -->
      <div class=" d-block mr-auto ml-auto" id="imageDiv">
        <img class="" id="image" src="./assets/img/woman2.jpg" alt="">
      </div>
      
      
      <div id="icons" style="" class="d-md-none d-sm-none d-lg-block">
        <img id="commentIcon" src="./assets/img/comment.png" alt="">
        <span>deere</span>
        <img id="instagramIcon" class="d-block" src="./assets/img/instagram.png" alt="">
        <span>deere</span>
        <img id="twitterIcon" class="d-block" src="./assets/img/twitter.png" alt="">
        <span v-for="social in social_media" :key="social.twitter">{{social.twitter}}</span>
        <img id="snapchatIcon" class="d-block" src="./assets/img/snapchat.png" alt="">
        <img id="gmailIcon" class="d-block" src="./assets/img/gmail.png" alt="">
      </div>

      <div id="mobileIcons" class="d-flex justify-content-center d-lg-none ">
        <img id="mvinstagramIcon" class="d-flex" src="./assets/img/instagram.png" alt="">
        <!-- <p class="d-flex" v-for="data in datas" :key="data.social_media.twitter">{{data.social_media}}oooppp</p> -->
        <!-- <h4 class=" text-white" v-for="data in datas" :key="data.social_media">{{data.social_media.twitter}}</h4> -->
        <img id="twitterIcon" class="d-flex ml-4" src="./assets/img/twitter.png" alt="">
        <img id="snapchatIcon" class="d-flex ml-4" src="./assets/img/snapchat.png" alt="">
        <img id="gmailIcon" class="d-flex ml-4" src="./assets/img/gmail.png" alt="">

      </div>

      <div class="d-flex justify-center " id="navbarContent">
        <b-navbar  class="text-white " >
          <b-navbar-nav class="text-white">
            <b-nav-item class="mt-4 " id="home" href="#">HOME</b-nav-item>

            <!-- Navbar dropdowns -->
            <b-nav-item class="ml-4 mt-4  " id="about" href="#">ABOUT</b-nav-item>
            <b-nav-item href="#">
              <div id="navImgDiv" class="d-block mr-auto ml-auto">
                <img class="d-block " id="navImg" src="./assets/img/woman.jpg" alt="">
              </div>
            </b-nav-item>
            <b-nav-item class="d-block  mt-4 ml-10" id="gallery" href="#">GALLERY</b-nav-item>
            <b-nav-item class="ml-4 mt-4  " id="contact" href="#">CONTACT</b-nav-item>
          </b-navbar-nav>
        </b-navbar>
        
      </div>
      
    <!-- </div> -->
   
   
      
    
    
  </div>
</template>


<script>
import axios from 'axios'
export default {
  name: 'App',
  components: {
  
  },
  data(){
    return{
      datas:null,
      social_media:null
    }
  },
  mounted(){
    axios.get('https://hirng-x2021.glitch.me/api')
    .then(response =>{
    (this.datas = response);
    this.social_media = response;

    
    });
    // console.log(this.datas);
  }
 
}
</script>

<style>
@import url(https://fonts.google.com/specimen/Sintony);
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  
  color: #2c3e50;
}
.nameDiv{
  /* position:relative; */
}
.nameDiv h2{
  /* position: absolute; */
  /* transform: translate(-50%, -50%); */
  
}

#contact{
  margin-left: 100px;
}
#name{
  font-family: Sintony;
  /* transform: translate(-50%, -50%); */
  /* z-index: 0;
  top: -140px; */
  font-size: 3rem;
  word-spacing: 4px;
  letter-spacing: 5px;
}
/* #name:nth-child(1){
  color: transparent;
  -webkit-text-stroke: 2px #03a9f4;
}
#name:nth-child(2){
  color: #03a9f4;
  animation: animate 4s ease-in-out infinite;
}
@keyframes animate{
  0%,100%
  {
    clip-path:polygon(0% 45%, 15% 44%, 32% 50%, 54% 60%, 
    70% 61%, 84% 59%, 100% 52%,
    100% 100%, 0% 100%);
  }
  50%
  {
    clip-path: polygon(0% 45%, 15% 44%, 32% 50%,
    54% 60%, 70% 61%, 84% 59%, 100% 52%, 100% 100%, 0% 100%);
  }
} */
#overallDiv{
  background: linear-gradient(to right, #b8052e 50%, #c90432e0 50%);
  max-height: 100%;
}
#imageDiv{
  height: 52vh;
  width: 80vh;
  top: 50%;
  left: 50%;
  margin-top: 20vh;
  box-shadow: 15px 2px  8px 5px  rgba(63, 3, 3, 0.126);
  background-color: #c90432e0;
}
 #gallery{
  margin-left: 270px;
   transform: translate(-10%, 0%);
}
#home{
  transform: translate(80%, 0%);
}
#about{
  margin-right: -148px;
  transform: translate(80%, 0%);
}
#contact{
   transform: translate(-8%, 0%);
}
#image{
  /* height: 100%; 
  */
  /* max-width: 80vh;
  max-height: 70vh;*/
  background-position: absolute; 
  max-height: 100%;
  width: 700px;
  
}
#commentIcon{
  width: 70px;
}
#navbarContent{
  margin-top: 40px;
  font-size: 30px;
  font-family: Sintony;
}
#mobileIcons{
  
  z-index: 0; 
  top:650px;
  left: 0;
  position: absolute;

}
#icons{
  position: absolute;
  right: 0;
  margin-right: 34px;
  margin-top: -380px;
  
}
#navImgDiv{
  /* background-color: red; */
  transform: translate(40%, 40%);
  padding-left: 0px;
}
#navImg{
  border-radius: 50%;
  width: 100px;
  height: 120px;
  position: relative;
  transform: translate(150%, -50%);
  padding-right: 4px;
  
  
 
  margin-left: 72px;
  
  
}
#instagramIcon{
  width: 60px;
  cursor: pointer;
}
#snapchatIcon{
  width: 60px;
  margin-top:20px;
  cursor: pointer;
}
#twitterIcon{
  width: 60px;
  margin-top:20px;
  cursor: pointer;
}
#gmailIcon{
  width: 60px;
  margin-top:20px;
  cursor: pointer;
}
#mvinstagramIcon{
  width: 60px;
  height: 56px;
  margin-top: 25px;
  margin-left: 100%;
}
  @media(max-width:991px) {
    #navImg{
      margin-left: 55px;
      width: 160px;
      height: 90px;
      
      
    }
    #gallery{
      
    }
    #contact{
     transform: translate(-30%, 0%);
      color: white;
    }
    #home{
      transform: translate(10%, 0%);
    }
    #about{
      transform: translate(80%, 0%);
    }
    
    #navImgDiv{
  /* background-color: red; */
    transform: translate(180%, 40%);
    padding-left: 0px;
  }
    #mobileIcons{
  
    z-index: 0; 
    top:650px;
    left: 0;
    position: absolute;

}
    #navbarContent{
      display: flex;
    }
     /* #gallery{
      margin-right: 120px;
    } */
    /*
    #about{
      margin-left: 2px;
    }
    #home{
      margin-left: 30px;

    } */
    /* #contact{
      margin-left:5px;
    } */
    }
</style>
