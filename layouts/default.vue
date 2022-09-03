<template>
  <v-app light style="background-color: #1A202C; padding-left: 12rem; padding-right: 12rem">
    <div style="margin-left: 90px; margin-right: 90px">
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
</style>
