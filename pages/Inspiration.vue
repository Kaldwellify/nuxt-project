<template>
    <b-container class="inspirationContainer">
        <Card
            v-for="workoutQuote of quote"
            :key="workoutQuote.id"
            :workoutQuote="workoutQuote"
            />
    </b-container>
</template>


<script>
import Card from '~/components/Card.vue'
import axios from 'axios';

export default {
    components: {
        Card
    },
    data() {
        return {
            loading: true,
            quote: null,
            errored: false
        }
    },
    mounted() {
        axios
            .get('https://type.fit/api/quotes')
            .then(
                response => {
                    this.quote = response.data
                    }
                )
            .catch(error => {
            console.log(error);
            this.errored = true;
        })
            .finally(() => this.loading = false);
    },
      head() {
      return {
        meta: [
          {
            hid: 'description',
            name: 'description',
            content: 'Get inspired with this HUGE list of inspirational quotes!'
          }
        ]
      }
    }
}
</script>

<style>
.inspirationContainer {
    display: grid;
grid-template-columns: repeat(3, 1fr);
grid-template-rows: repeat(3, 1fr);
grid-column-gap: 0px;
grid-row-gap: 0px; 
  min-height: 200px;
  max-width: 85%;
  margin-top: 4rem;
  justify-content: center;
  text-align: center;
}
</style>