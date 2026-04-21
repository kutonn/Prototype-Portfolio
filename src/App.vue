<template>
  <div id="app">
    <!-- Navbar ONLY for portfolio pages -->
    <Navbar v-if="$route.path.startsWith('/portfolio')" />
    <router-view />
  </div>
</template>

<script>
import Navbar from './components/Navbar.vue'

export default {
  components: {
    Navbar
  }
}
</script>
