<template>
    <div id="app">
        <pre>{{ workouts }}</pre>
    </div>
</template>


<script>
import axios from 'axios';

export default {
    data() {
        return {
            loading: null,
            workouts: null,
            errored: false,
            query: ''
        }
    }
}

methods: 
{
   function getData() {
        axios
        .get(`https://exercisedb.p.rapidapi.com/exercises/bodyPartList?api_key=327744d0b4msh1e58914cc329eeep13f2c3jsn0c3913839a3c`)
        .then(response => (this.workouts = response.data.results[0].known_for))
        .catch(error => {
            console.log(error)
            this.errored = true
    })
        .finally(() => this.loading = false)
    }
};
</script>