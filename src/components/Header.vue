<template>
      <nav class="navbar navbar-expand-lg navbar-dark bg-dark mb-5">
          <router-link to="/" class="navbar-brand">Vue.JS Application</router-link>
  <button class="navbar-toggler" type="button" data-toggle="collapse" data-target="#navbarSupportedContent" aria-controls="navbarSupportedContent" aria-expanded="false" aria-label="Toggle navigation">
    <span class="navbar-toggler-icon"></span>
  </button>

  <div class="collapse navbar-collapse" id="navbarSupportedContent">
    <ul class="navbar-nav ml-auto">
      <li class="nav-item active">
           <router-link to="/" class="nav-link">Home</router-link>
      </li>
    </ul>
  </div>
</nav>
</template>

<script>
export default {
  name: 'Header',
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>

</style>
