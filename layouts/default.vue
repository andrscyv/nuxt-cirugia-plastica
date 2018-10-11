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
  height="auto"
  
>
  <v-card
    flat
    tile
    class="blue-grey lighten-1 white--text text-xs-center"
  >
      <v-card-text>
        <!-- <v-btn
          v-for="icon in icons"
          :key="icon"
          class="mx-3 white--text"
          icon
        >
          <v-icon size="24px">{{ icon }}</v-icon>
        </v-btn> -->
      </v-card-text>

      <v-card-text class="white--text pt-0">
        Phasellus feugiat arcu sapien, et iaculis ipsum elementum sit amet. Mauris cursus commodo interdum. Praesent ut risus eget metus luctus accumsan id ultrices nunc. Sed at orci sed massa consectetur dignissim a sit amet dui. Duis commodo vitae velit et faucibus. Morbi vehicula lacinia malesuada. Nulla placerat augue vel ipsum ultrices, cursus iaculis dui sollicitudin. Vestibulum eu ipsum vel diam elementum tempor vel ut orci. Orci varius natoque penatibus et magnis dis parturient montes, nascetur ridiculus mus.
      </v-card-text>

      <v-divider></v-divider>

      <v-card-text class="white--text">
        &copy;2018 — <strong>Dr. Andrés Cruz</strong>
      </v-card-text>
  </v-card>
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
        title: 'Vuetify.js',
        icons: [
        'fab fa-facebook',
        'fab fa-twitter',
        'fab fa-google-plus',
        'fab fa-linkedin',
        'fab fa-instagram'
      ]
      }
    }
  }
</script>
<style>
*{
  font-family:'Source Sans Pro', sans-serif;
}
</style>

