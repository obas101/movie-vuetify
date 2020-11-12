<template>
  <nav>
    <v-app-bar flat app>
      <v-app-bar-nav-icon
        color="orange"
        @click="drawer = !drawer"
      ></v-app-bar-nav-icon>

      <v-toolbar-title class="text-uppercase orange--text" flat>
        <v-icon></v-icon>
        <span class="font-weight-light">movie</span>
        <span>app</span>
      </v-toolbar-title>

      <v-spacer></v-spacer>
      <v-btn text color="orange">my watchlist</v-btn>
      <v-spacer></v-spacer>

      <v-btn text color="orange"><span>SignUp</span></v-btn
      >|
      <v-btn text color="orange"><span>LogOut</span></v-btn>
    </v-app-bar>

    <v-navigation-drawer v-model="drawer" app dark>
      <v-list dense rounded>
        <v-subheader><v-icon>apps</v-icon>CATEGORIES</v-subheader>
        <v-list-item-group>
          <v-list-item v-for="list in lists" :key="list.id">
            <v-list-item-icon>
              <v-icon>{{ list.icon }}</v-icon>
            </v-list-item-icon>
            <v-list-item-content
              ><v-list-item-title>{{
                list.title
              }}</v-list-item-title></v-list-item-content
            >
          </v-list-item>
        </v-list-item-group>
      </v-list>
    </v-navigation-drawer>
  </nav>
</template>

<script>
export default {
  data() {
    return {
      drawer: false,
      lists: [
        { id: 1, title: 'MOVIES', icon: 'live_tv', link: '/movies' },
        { id: 2, title: 'SERIES', icon: 'live_tv', link: '/tv-series' },
        { id: 3, title: 'TRENDING', icon: 'trending_up', link: '/trending' },
      ],
    }
  },
}
</script>
