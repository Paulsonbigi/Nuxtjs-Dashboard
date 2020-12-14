<template>
    <v-main>
        <v-row>
            <div class="board-wrap">
                <div>
                    <h1>Dashboard</h1>
                    <h6>monday 02 March 2020</h6>
                </div>
                <div class="alerts">
                    <span><fa icon="envelope"/></span>
                    <span><fa icon="bell"/></span>
                    <span class="select">
                        <h5>mm</h5>
                        <span>
                            <v-select
                                :items="userOptions"
                                label="user"
                                dense
                                flat
                                height="30"
                                class="list-select"
                                >
                                    <template v-slot:item="slotProps">
                                        <p>{{slotProps.item}}</p>
                                    </template>
                                </v-select>
                        </span>
                    </span>
                </div>
            </div>
        </v-row>
    </v-main>
</template>

<script>

export default {
    data(){
        return{
            userOptions: [
                "username",
                "Sign in",
                "Sign up"
            ]
        }
    }
}
</script>

<style scoped>
.board-wrap{
    display: flex;
    width: 100%;
    padding: 20px;
    justify-content: space-between;
}
.alerts{
    display: flex;
    align-items: center;
    justify-content: space-between;
    width: 20%;
    color: #5144a6;
    font-size: 12px;
}
.select{
    display: flex;
    align-items: center;
}
.list-select{
    width: 60px;
    /* height: 30px; */
    align-items: center;
    margin-left: 10px;
    font-size: 7px !important;
}
.list-select label{
    font-size: 9px !important;
}
@media(max-width: 500px){
    .alerts{
        width: 35%;
        font-size: 9px;
    }
    .board-wrap h1{
        font-size: 20px;
    }
    .list-select{
        width: 50px;
        height: 30px;
        font-size: 8px !important;
    }
}
</style>