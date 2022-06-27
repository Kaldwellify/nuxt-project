<script>
    export default {
        props: {
            workoutQuote: Object
        }
    }
</script>

<template>
    <article class="card">
        <h2 class="card_title">{{ workoutQuote.text }}</h2>
        <p class="card_sub">{{ workoutQuote.author }}</p>
    </article>
</template>

<style>
.card {
  text-align: center;
  margin: 1rem;
  border: 2px solid #000;
  padding: 1.5rem;
  width: 85%;
  height: auto;
}
.card_title {
    font-size: 1.5rem;
    margin-bottom: .25rem;
    font-style: bold;
  }
.card_copy {
    font-size: 0.875rem;
  }
</style>