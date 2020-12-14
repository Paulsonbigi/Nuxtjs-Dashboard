<template>
    <v-main class="main-container">
        <v-row>
            <v-col cols="12">
                <DashboardHeader/>
            </v-col>
        </v-row>
        <v-row>
            <v-col>
                <BoardIntro/>
            </v-col>
        </v-row>
        <v-row class="detail-row">
            <v-container mt="10">
                <h5>Overview</h5>
            </v-container>
            <v-col v-for="detail in details"
                :key="`${detail.title}`" cols="12" sm="6" md="3">
                    <Overview
                    :detail="detail"
                />
            </v-col>
        </v-row>
        <v-row class="operation-row">
            <v-col v-for="PostOperation in PostOperations" 
                :key="`${PostOperation.title}`" cols="12" sm="12" md="12">
                <Posts
                    :PostOperation="PostOperation"
                />
            </v-col>
        </v-row>
    </v-main>
</template>

<script>
import DashboardHeader from "../components/DashboardHeader"
import Overview from "../components/Overview"
import BoardIntro from "../components/BoardIntro"
import Posts from "../components/Posts"
import people from "../assets/people.png"
import sitting from "../assets/sitting.png"
export default {
    components: {
        DashboardHeader,
        Overview,
        BoardIntro,
        Posts
    },
    data(){
        return {
            details: [
                {rating: "83%", title: "Open Rate", color: "#f2cc5d", iconImg: "wave-square"},
                {rating: "77%", title: "Completed", color: "#5144a6", iconImg: "check-circle"},
                {rating: "91", title: "Unique Views", color: "#f266a7", iconImg: "star"},
                {rating: "126", title: "Total Views", color: "#d8d0f2", iconImg: "eye"}
            ],
            PostOperations: [
                {
                    title: "Next in Fashion", 
                    imgUrl: require("../assets/people.png"), 
                    slides: 10,
                    color: "#f266a7",
                    status: "Public",
                    description: "Sorry about what happened at corporate, but I am glad you are back! - Max"
                },
                {
                    title: "Digital Marketing Today", 
                    imgUrl: require("../assets/sitting.png"),
                    slides: 10,
                    color: "#5144a6",
                    status: "Private",
                    description: "Sorry about what happened at corporate, but I am glad you are back! - Max"
                }
            ]
        }
    }
}
</script>

<style scoped>
.detail-row, .operation-row{
    margin-top: 50px;
}
@media(max-width: 500px) {
    .main-container{
        padding: 20px !important;
    }
}
</style>