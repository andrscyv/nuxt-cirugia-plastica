<template>
  <v-app >
    <v-navigation-drawer
      v-model="drawer"
      temporary
      app
    >
      <v-list>
        <v-list-tile
          v-for="(item, i) in items"
          :to="item.to"
          :key="i"
          router
          exact
        >
          <v-list-tile-action>
            <v-icon v-html="item.icon" />
          </v-list-tile-action>
          <v-list-tile-content>
            <v-list-tile-title v-text="item.title" />
          </v-list-tile-content>
        </v-list-tile>
      </v-list>
    </v-navigation-drawer>

    <v-toolbar
      :clipped-left="clipped"
      fixed
      app
      color = "white"
    >
    <a  href="/">
                <img src="/img/logo-simple.png" class="mb-1 " width="88" height="40" alt="">
    </a>
      <v-toolbar-items class="hidden-sm-and-down">
      <v-btn v-for="(item, i) in items"
          :to="item.to"
          :key="i"
          flat 
          nuxt
          >
          {{item.title}}
          </v-btn>
    </v-toolbar-items>
    <v-spacer></v-spacer>
    <v-toolbar-side-icon @click="drawer = !drawer" class="hidden-md-and-up" />
    </v-toolbar>

    <v-content>
      <v-container>
        <nuxt />
      </v-container>
    </v-content>
    
    <v-footer
      :fixed="fixed"
      app
    >
      <span>&copy; 2017</span>
    </v-footer>
  </v-app>
</template>

<script>
  export default {
    data() {
      return {
        clipped: true,
        drawer: false,
        fixed: false,
        items: [
          { title: 'Inicio', to: '/' }
        ],
        miniVariant: false,
        right: false,
        rightDrawer: false,
        title: 'Vuetify.js'
      }
    }
  }
</script>
<style>
*{
  font-family:'Source Sans Pro', sans-serif;
}
</style>

