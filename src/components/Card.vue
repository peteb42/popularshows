<template>
    <!-- This vue template will hold the 4 cards from four of the popular tv shows in api variable -->
    <div class="col">
        <div class="card" v-for="result in results" :key="result.id">
            <img v-bind:src="'http://image.tmdb.org/t/p/w154/' + result.poster_path" class="card-img-top" alt="blank">
        
            <div class="card-body" >
                <h4>{{result.name}}</h4>
                <p>{{result.overview}}</p>
            </div>
        
        </div>
    </div>
</template>

<script>
// Axios will need to be imported to get api data from the TMDB
import axios from 'axios';
// Define variables in vue instance
export default {
    name: 'Card',
    data() {
        return {
            results:""
            
        }
    },
    

    mounted() {
        axios.get("https://api.themoviedb.org/3/tv/popular?api_key=7a382377ded02d04b294930106237183&language=en-US&page=1")
        .then((response) => {
            this.results = response.data.results.slice(0,4);
        })
  }
}
</script>

<style scoped>
.card {
    width: 18rem;
    display:inline-block;
}
.col {
    display: flex;
    margin-top: 60px;
    margin-left:5.7rem;
}

</style>