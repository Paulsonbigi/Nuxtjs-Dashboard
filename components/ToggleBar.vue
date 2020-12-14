<template>
  <v-card
    width="50%"
    height="100%"
    flat
    color="#d8d0f2"
    class="mx-auto sideDrawer"
  >
  <div class="main-container">
      <div class="input-field">
            <v-text-field
                v-model="search"
                label="Create New Pitch"
                flat
                height="70px"
                class="text-field"
                solo
              >
              </v-text-field>

                <v-btn
                    class="mx-auto"
                    fab
                    dark
                    small
                    color="indigo"
                  >
                    <v-icon dark>
                      mdi-plus
                    </v-icon>
                  </v-btn>
          </div>
    <ul class="link-list" v-for="link in links" :key="link.label">
        <li class="link">
            <fa class="one-font" :icon="link.urlLogo"/><nuxt-link :to="link.urlLink" >{{link.label}}</nuxt-link>
        </li>
    </ul>
    <div class="advert">
        <div class="ads-img"></div>
        <p>Lorem ipsum dolor sit amet consectetur, soluta.</p>
        <v-btn
            class="upgrade-btn">Upgrade</v-btn>
    </div>
    </div>
  </v-card>
</template>

<script>
  export default {
    props: {
        links: {
        type: Object,
        required: true
        }
    }
  }
</script>

<style scoped>
.sideDrawer{
  top: 0px;
  left: 0px;
  z-index: 100;
  height: 100%;
  position: absolute;
  display: flex;
  flex-direction: column;
  transition: 1s ease-in-out;
}
.main-container{
    margin-top: 50px;
    height: 700px;
    position: relative;
}
.input-field{
    padding: 10px;
  display: flex;
  height: 90px;
}
.link-list{
    list-style: none;
}
.link{
    padding: 20px 10px;
    display: flex;
    align-items: center;
}
.link .one-font{
    margin-right: 10px;
    color: #574888;
}
.link a{
    text-decoration: none;
    color: #574888;
    font-weight: 500;
}
.link:hover{
    background: #2e254b;
    transition: 1s ease-in-out;
}
.link a:hover{
    color: #ffffff;
}
.text-field{
    margin-right: 5px;
}
.upgrade-btn{
  background: #574888 !important;
  color: #ffffff;
  text-transform: capitalize;
  box-shadow: none;
  font-size: 12px;
  height: 30px !important;
}
.advert{
  border-radius: 10px;
  display: flex;
  flex-direction: column;
  justify-content: center;
  padding: 30px;
  background: #e6deff;
  bottom: 20px;
  margin: 50px 20px;
}
.advert p{
  text-align: center;
  margin:  20px 0px;
  font-size: 9px;
}
</style>