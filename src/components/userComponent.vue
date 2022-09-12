<template>
    <div :class="[ male() ? 'card' :'femaleCard']">
        <img :src="this.user[0].picture.large" alt="Avatar" style="width:100%">
        <div class="container">
            <h4><b>{{this.user[0].name.first}} {{this.user[0].name.last}}</b></h4> 
            <p>{{this.user[0].location.country}}</p> 
            <p>{{this.user[0].gender}}</p> 
        </div>
    </div>
</template>

<script>
    import axios from 'axios'
    export default {
        data(){
            return{
                user:{},
            }
        },
        created() {
            this.loadUser();
        },
        methods: {
            loadUser(){
                axios
                    .get("https://randomuser.me/api/?resuslts=1")
                    .then((response) => (this.user = response.data.results));
            },
            male(){
                if(this.user[0].gender == 'male'){
                    return true
                }else return false
            }
        },
    }
</script>

<style scoped>
.card {
    margin-top: 40px;
    box-shadow: 0 4px 8px 0 rgba(0,0,0,0.2);
    transition: 0.3s;
    width: 100%;
    margin-left: auto;
    margin-right: auto;
}
.femaleCard {
    margin-top: 40px;
    box-shadow: 0 4px 8px 0 rgba(0,0,0,0.2);
    transition: 0.3s;
    width: 100%;
    margin-left: auto;
    margin-right: auto;
}
.femaleCard:hover {
    box-shadow: 0 8px 16px 0 rgba(248, 5, 236, 0.2);
}
.card:hover {
    box-shadow: 0 8px 16px 0 rgba(8, 108, 223, 0.2);
}

.container {
    padding: 2px 12px;
}
</style>