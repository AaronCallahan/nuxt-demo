<template>
  <v-app>
    <v-toolbar
      :clipped-left="clipped"
      fixed
      app >
      <v-toolbar-side-icon />
      <v-toolbar-title>Carl v2</v-toolbar-title>
      <img 
        class="carl-img"
        src="carl.png">
      <v-spacer />
      <v-toolbar-items class="navbar-links">
        <v-btn flat><nuxt-link to="/">Accounts</nuxt-link></v-btn>
        <v-btn flat><nuxt-link to="/dashboards">Dashboards</nuxt-link></v-btn>
        <v-btn flat><nuxt-link to="/salescrm">Sales CRM Users</nuxt-link></v-btn>
        <v-btn flat><nuxt-link to="/codex">Codex</nuxt-link></v-btn>
        <v-btn flat><nuxt-link to="/bugs">Bugs</nuxt-link></v-btn>
        <v-btn flat><nuxt-link to="/performance">Performance</nuxt-link></v-btn>
        <v-btn flat><nuxt-link to="/product">Product</nuxt-link></v-btn>
        <v-btn flat><nuxt-link to="/discovery">Customer Discovery</nuxt-link></v-btn>
        <v-btn flat><nuxt-link to="/mail">Mail</nuxt-link></v-btn>
      </v-toolbar-items>
    </v-toolbar>
    <v-content>
      <v-container fluid>
        <nuxt />
      </v-container>
    </v-content>
    <v-footer
      :fixed="fixed"
      app >
      <span>&nbsp; &copy; 2019</span>
    </v-footer>
  </v-app>
</template>

<script>
export default {
  data() {
    return {
      clipped: false,
      drawer: true,
      fixed: false
    }
  }
}
</script>

<style lang="scss" scoped>
  .carl-img {
    position: absolute;
    bottom: 0;
    left: 90px;
  }

  .navbar-links a {
    text-decoration: none;
  }
</style>
