<template>
  <v-app>
    <div class="main-container">
      <div class="sidebar" v-if="mobileView">
        <ToggleBar :links="links" :class="{'open': !showNav}"/>
      </div>
      <div class="nav-icon" v-if="mobileView" @click="showNav =!showNav">
        <v-app-bar-nav-icon color="#2e254b" rounded></v-app-bar-nav-icon>
      </div>
      <div class="navigator" v-if="!mobileView">
        <SideBar :links="links"/>
      </div>
      <div class="main-body">
          <nuxt />
      </div>
    </div>
  </v-app>
</template>

<script>
import Sidebar from "../components/SideBar"
import ToggleBar from "../components/ToggleBar"
export default {
  components: {
    Sidebar,
    ToggleBar
  },
  data(){
    return{
      mobileView: false,
      showNav: false,
      links: [
      {
        label: "Home",
        urlLink: "/",
        urlLogo: "home"
      },
      {
        label: "Dashboard",
        urlLink: "/dashboard",
        urlLogo: "columns"
      },
      {
        label: "Leads",
        urlLink: "/leads",
        urlLogo: "users"
      },
      {
        label: "Editor",
        urlLink: "/editor",
        urlLogo: "edit"
      },
      {
        label: "Setting",
        urlLink: "/setting",
        urlLogo: "cog"
      },
      {
        label: "Preview",
        urlLink: "/preview",
        urlLogo: "glasses"
      }
    ],
    }
  },
  methods: {
    handleView(){
      this.mobileView = window.innerWidth <= 769;
    }
  },
  created(){
    this.handleView();
    window.addEventListener('resize', this.handleView)
  }
}
</script>

<style scoped>
.main-container{
  width: 100%;
  display: flex;
}
.navigator{
  position: fixed;
  top: 0px;
  width: 20%;
}
.main-body{
  width: 80%;
  padding: 20px;
  margin-left: 20%;
}
@media(max-width: 769px){
  .main-container{
    flex-direction: column;
  }
 .main-body{
   padding: 0px;
    width: 100%;
    margin-left: 0px;
  } 
  .nav-icon{
    position: absolute;
    top: 10px;
    z-index: 200;
    right: 20px;
  }
  .open{
    transform: translate(-800px);
  }
}
</style>