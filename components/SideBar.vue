<template>
  <v-card
    height="100vh"
    class="mx-auto"
    flat
  >
    <v-navigation-drawer permanent>
        

      <v-list
        dense
        nav
      >
        <div class="main-container">
          <div class="input-field">
            <v-text-field
                v-model="search"
                label="Create New Pitch"
                flat
                class="text-field"
                solo-inverted
              >
              </v-text-field>

              <v-btn
                  class="mx-auto"
                  fab
                  dark
                  small
                  color="#574888"
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
      </v-list>

    </v-navigation-drawer>
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
.main-container{
    display: flex;
    flex-direction: column;
    margin-top: 100px;
    justify-content: center;
    height: 700px;
    position: relative;
}
.input-field{
  display: flex;
  padding: 0 10px;
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
  height: 50px;
  background: #c9bfeb;
  opacity: 0.2;
  padding: 1px;
  color: #ffffff !important;
  margin-right: 5px;
}
.upgrade-btn{
  background: #574888 !important;
  color: #ffffff;
  text-transform: capitalize;
  box-shadow: none;
}
.advert{
  border-radius: 10px;
  display: flex;
  flex-direction: column;
  justify-content: center;
  padding: 30px;
  background: #e6deff;
  margin:  0 20px;
}
.advert p{
  text-align: center;
  margin:  20px 0px;
}
</style>