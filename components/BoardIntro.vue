<template>
    <v-main>
        <v-card
            elevation="0"
            light
            class="main-card"
            color="#d8d0f2"
        >
            <v-card-text>
                <div class="card-display">
                    <h1>Hi, Alyssa</h1>
                    <p>Ready to start your day with some pitch desks?</p>
                </div>
            </v-card-text>
            <v-img src="" alt=""/>
        </v-card>
    </v-main>
</template>

<style scoped>
.main-card{
    box-shadow: none !important;
}
.card-display{
    padding: 50px 0px;
    background-image: url(../assets/girl.png);
    background-position: right;
    background-size: 50%;
    background-repeat: no-repeat;
}
.card-display h1{
    line-height: 2;
    color: #000000;
}
.card-display p{
    color: #000000;
}
@media(max-width: 500px){
    .card-display h1{
        font-size: 20px;
        line-height: 2;
    }
    .card-display p{
        font-size: 8px;
        width: 50%;
        line-height: 1.5;
    }
}
</style>