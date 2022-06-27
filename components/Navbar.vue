<template>
  <!-- Nav -->
  <b-navbar toggleable="lg" type="dark" variant="info" fixed="top">
    <b-navbar-toggle target="nav-collapse"></b-navbar-toggle>
    <b-collapse id="nav-collapse" is-nav>
      <b-navbar-nav class="ml-auto">
        <nuxt-link to="/" class="nav-link">
          Home
          <span class="sr-only">(current)</span>
        </nuxt-link>
        <nuxt-link to="/images" class="nav-link">Workout Types</nuxt-link>
        <nuxt-link to="/inspiration" class="nav-link">Get Inspired</nuxt-link>
      </b-navbar-nav>
    </b-collapse>
  </b-navbar>
  <!-- Nav End -->
</template>

<script>
export default {
  name: "Navbar",
};
</script>

<style>
.logo {
  width: 15%;
}
</style>


