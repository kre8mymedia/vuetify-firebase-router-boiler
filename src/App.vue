<template>
  <v-app id="inspire">
    <v-navigation-drawer
      v-model="drawer"
      app
      clipped
      temporary
    >
      <v-list dense>

        <!-- Home page route -->
        <router-link to="/">
          <v-list-item link>
            <v-list-item-action>
              <v-icon>mdi-view-dashboard</v-icon>
            </v-list-item-action>
            <v-list-item-content>
              <v-list-item-title>Dashboard</v-list-item-title>
            </v-list-item-content>
          </v-list-item>
        </router-link>
        <!-- END Home page route -->

        <!-- View Meetups route -->
        <router-link to="/meetups">
          <v-list-item link>
            <v-list-item-action>
              <v-icon>mdi-account-supervisor</v-icon>
            </v-list-item-action>
            <v-list-item-content>
              <v-list-item-title>View Meetups</v-list-item-title>
            </v-list-item-content>
          </v-list-item>
        </router-link>
        <!-- END View Meetups page route -->

        <!-- View Meetups route -->
        <router-link to="/meetup/new">
          <v-list-item link>
            <v-list-item-action>
              <v-icon>mdi-map-marker</v-icon>
            </v-list-item-action>
            <v-list-item-content>
              <v-list-item-title>Organize Meetup</v-list-item-title>
            </v-list-item-content>
          </v-list-item>
        </router-link>
        <!-- END View Meetups page route -->

        <!-- View Meetups route -->
        <router-link to="/profile">
          <v-list-item link>
            <v-list-item-action>
              <v-icon>mdi-account</v-icon>
            </v-list-item-action>
            <v-list-item-content>
              <v-list-item-title>Profile</v-list-item-title>
            </v-list-item-content>
          </v-list-item>
        </router-link>
        <!-- END View Meetups page route -->

        <!-- View Meetups route -->
        <router-link to="/login">
          <v-list-item link>
            <v-list-item-action>
              <v-icon>mdi-lock</v-icon>
            </v-list-item-action>
            <v-list-item-content>
              <v-list-item-title>Login</v-list-item-title>
            </v-list-item-content>
          </v-list-item>
        </router-link>
        <!-- END View Meetups page route -->

        <!-- View Meetups route -->
        <router-link to="/register">
          <v-list-item link>
            <v-list-item-action>
              <v-icon>mdi-account-plus</v-icon>
            </v-list-item-action>
            <v-list-item-content>
              <v-list-item-title>Register</v-list-item-title>
            </v-list-item-content>
          </v-list-item>
        </router-link>
        <!-- END View Meetups page route -->

        <!-- About page route -->
        <router-link to="/settings">
          <v-list-item link>
            <v-list-item-action>
              <v-icon>mdi-settings</v-icon>
            </v-list-item-action>
            <v-list-item-content>
              <v-list-item-title>Settings</v-list-item-title>
            </v-list-item-content>
          </v-list-item>
        </router-link>
        <!-- END About page route -->

      </v-list>
    </v-navigation-drawer>

    <!-- NAVBAR -->
    <v-app-bar
      app
      clipped-left
      color="#1867c0"
    >
      <v-app-bar-nav-icon @click.stop="drawer = !drawer" />
        <v-toolbar-title>
          <router-link to="/" tag="span" style="cursor:pointer">
            Application
          </router-link>
        </v-toolbar-title>
      <v-spacer></v-spacer>

      <!-- items right of hamburger button -->
      <v-toolbar-items>
        <!-- <v-btn icon>
          <v-icon>mdi-magnify</v-icon>
        </v-btn> -->
        <!-- Right-side dropdown -->
        <v-menu
        left
        bottom
        >
          <template v-slot:activator="{ on }">
            <v-btn icon v-on="on">
              <v-icon>mdi-dots-vertical</v-icon>
            </v-btn>
          </template>

          <v-list>
            <v-list-item
              v-for="n in 2"
              :key="n"
              @click="() => {}"
            >
              <v-list-item-title>Option {{ n }}</v-list-item-title>
            </v-list-item>
          </v-list>
      </v-menu>
      <!-- END Right-side dropdown -->
      </v-toolbar-items>
      <!-- END items right of hamburger button -->

    </v-app-bar>
    <!-- END NAVBAR -->

    <v-content>
     <main>
       <router-view></router-view>
     </main>
    </v-content>

    <v-footer 
    app
    color="#1867c0"
    >
      <span>&copy; 2019</span>
    </v-footer>
  </v-app>
</template>

<script>
  export default {
    props: {
      source: String,
    },
    data: () => ({
      drawer: null,
    }),
    created () {
      this.$vuetify.theme.dark = true
    },
  }
</script>

<style lang="scss">
  @import '@/scss/main';
</style>
