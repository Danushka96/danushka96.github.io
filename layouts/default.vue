<template>
  <v-app light class="container1">
    <div class="navbarContainer">
      <TopNavbar class="float-right"/>
    </div>
    <v-main>
      <v-container class="pa-6">
        <Nuxt/>
      </v-container>
    </v-main>
    <v-footer
      app
    >
      <span>&copy; {{ new Date().getFullYear() }} KLASS.LK</span>
    </v-footer>
  </v-app>
</template>

<script>
export default {
  name: 'DefaultLayout'
}
</script>
<style>
body {
  font-family: Overpass, system-ui, -apple-system, BlinkMacSystemFont, Segoe UI, Roboto, Helvetica Neue, Arial, Noto Sans, sans-serif, Apple Color Emoji, Segoe UI Emoji, Segoe UI Symbol, Noto Color Emoji;
}

.container1 {
  background-color: #1A202C; padding-left: 6rem; padding-right: 6rem
}

.navbarContainer {
  margin-left: 90px; margin-right: 90px
}

@media (max-width: 768px) {
  .container1 {
    padding: 0;
  }
  .navbarContainer {
    margin-left: 10px;
    margin-right: 10px;
  }
}
</style>
