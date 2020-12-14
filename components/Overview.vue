<template>
    <div class="main-wrap">
        <v-card
        elevation="0"
        dark
        class="main-card"
        :color="detail.color">
        <v-card-text>
            <div class="card-text">
                <div class="font-icon">
                    <p><fa class="one-font" :icon="detail.iconImg"/></p>
                </div>
                <v-spacer/>
                <div class="rating">
                    <h3>{{detail.rating}}</h3>
                    <h6>{{detail.title}}</h6>
                </div>
            </div>
            </v-card-text>
        </v-card>
    </div>
</template>

<script>
import { fas } from '@fortawesome/free-solid-svg-icons'
  export default {
    props: {
        detail: {
            type: Object,
            required: true
        }
    }
  }
</script>

<style scoped>
.main-card{
    margin-bottom: 40px;
    box-shadow: none !important;
}
.card-text{
    display: flex !important;
    align-items: center;
}
.font-icon{
    width: 50px;
    height: 50px;
    justify-content: center;
    align-items: center;
    display: flex;
    border-radius: 5px;
}
.font-icon p{
    color: #ffffff;
    font-size: 15px;
    display: flex;
    background: rebeccapurple;
    padding: 5px;
    align-content: center;
    justify-content: center;
    text-align: center;
}
.rating{
    color: #ffffff;
}
.one-font{
    font-size: 35px;
}
@media(max-width: 550px){
    .main-card{
        margin-bottom: 0px !important;
    }
    .one-font{
        font-size: 25px;
    }
}
</style>