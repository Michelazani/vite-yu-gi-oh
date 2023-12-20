<script>
import singleCard from './singleCard.vue';
import axios from 'axios';

export default {
    data() {
        return {
            list:[],
            apiUrl: 'https://db.ygoprodeck.com/api/v7/cardinfo.php?num=25&offset=0'
        }
    },
    name: 'cardList',
    components:{
    singleCard
    },
    methods: {
        getCards() {
            axios.get(this.apiUrl)
                .then((response) => {
                    // handle success
                    console.log(response.data.data);
                    this.list = response.data.data;
                })
                .catch(function (error) {
                    // handle error
                    console.log(error);
                })
        }
    },
    created(){
        this.getCards();
    }
}
</script>

<template>
    <section class="container">
        <div class="row">
            <h5>Found {{ list.length }} cards</h5>
        </div>

        <div class="row">
            <singleCard v-for="card in list" :key="card.id" :card="card"/>
        </div>
    </section>
</template>

<style lang="scss" scoped>
 @use '../style/general.scss' as *;
 @use '../style/partials/variables' as *;

section{
    background-color: $white;
    h5{
        background-color: $bg-dark;
        color: $white;
        padding: 1rem;
    }
}
    
</style>