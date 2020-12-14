<template>
    <v-main>
            <v-card
                elevation="0"
                class="post-card"
            >
            <div class="main-card">
                    <v-card class="img-container" :color="PostOperation.color">
                        <v-content>
                            <v-img class="imgUrl" :src="PostOperation.imgUrl" alt=""/>
                        </v-content>
                    </v-card>
                <v-container class="text-container">
                    <div class="card-text">
                        <div class="texts">
                            <h4 class="title">{{PostOperation.title}}</h4>
                            <p class="description">{{PostOperation.description}}</p>
                            <h6 class="slides">{{PostOperation.slides}} Slides</h6>
                        </div>
                        <v-card flat class="last-card">
                            <div class="post-icons">
                                <div class="switch-name">
                                    <span>{{PostOperation.status}}</span><v-switch
                                        flat
                                        dense
                                        class="switch"
                                        append-icon=""
                                        v-model="switch1"
                                        color="#5144a6"
                                        value=""></v-switch>
                                </div>
                                <div class="edit-icons">
                                    <fa class="one-font" icon="trash-alt"/>
                                    <fa class="one-font" icon="pencil-alt"/>
                                </div>
                            </div>
                        </v-card>
                    </div>
                </v-container>
                </div>
            </v-card>
        </v-main>
</template>

<script>
export default {
    props: {
            PostOperation : {
                type: Object,
                required: true
            }
    },
    data() {
        return {
            switch1: true,
            switch2: false
        }
    }
}
</script>

<style scoped>
.post-card{
    box-shadow: none !important;
    background: rgb(233, 233, 233);
}
.main-card{
    display: flex;
    align-content: center;
}
.img-container{
    display: flex;
    align-items: center;
    height: 200px;
    width: 200px;
    margin: auto;
    margin-left: 10px;
    padding: 10px;
    box-shadow: none !important;
}
.imgUrl{
    width: 200px;
    height: 200px;
    display: flex;
    align-items: center;
}

.card-text{
    display: flex;
    justify-content: space-between;
    align-items: center;
    height: 200px;
}
.last-card{
    width: 25%;
    margin-left: 5px;
    box-shadow: none;
    align-items: center;
    background: none !important;
}
.switch-name{
    width: 100%;
    display: flex;
    align-items: center;
}
.title{
    color: #5144a6;
}
.post-icons{
    width: 100%;
    margin-left: 5px;
    display: flex;
    flex-direction: column;
    align-items: center;
    justify-content: right !important;
}
.switch-section{
    display: flex;
}
.switch{
    size: 12px;
    width: 10px !important;
}

.edit-icons{
    color: #ffffff;
}
.one-font{
    margin: 3px;
}
@media(max-width: 500px){
    .img-container{
        display: flex;
        align-items: center;
        height: 120px;
        margin-left: 10px;
        padding: 10px;
        width: 100px !important;
    }
    .imgUrl{
        height: 100px;
        width: 100px;
    }
    .last-card{
        width: 100%;
    }
    .post-icons{
        width: 100%;
        position: relative;
        display: flex;
        flex-direction: row;
        justify-content: space-between;
        align-items: center !important;
        margin-left: 0px;
    }
    .text-container{
        padding: 10px !important;
    }
    .card-text{
        flex-direction: column;
        align-items: center;
        justify-content: space-between !important;
        height: 120px;
        padding: 0px;
    }
    .title{
        font-size: 12px !important;
        padding: 0px !important;
        margin: 0px !important;
        line-height: 1rem;
    }
    .description, .slides{
        font-size: 10px;
        margin: 0px;
    }
    .slides{
        margin-top: 5px;
    }
    .switch-name{
        width: 25%;
        height: 25px !important;
        display: flex;
        justify-content: space-between;
        align-items: center;
    }
    .switch-name span{
        font-size: 10px;
    }
    .edit-icons{
        position: absolute;
        right: 0px;
    }
}
</style>