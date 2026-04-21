<template>
  <nav>
    <router-link to="/portfolio/profile">Profile</router-link>
    <router-link to="/portfolio/showcase">Showcase</router-link>
    <router-link to="/portfolio/contact">Contact</router-link>
    <router-link to="/portfolio/creative">Creative</router-link>
  </nav>
</template>

<script>
export default {
  name: "Navbar"
};
</script>

<style scoped>
nav {
  display: flex;              /* use flexbox */
  justify-content: center;    /* center the links horizontally */
  gap: 1rem;                  /* spacing between links */
  padding: 1rem 0;            /* optional padding */
  font-weight: 500;
}

nav a {
  text-decoration: none;
  color: #5D8AA8;
  transition: color 0.2s;
}

nav a:hover {
  color: #004F98;
}
</style>
