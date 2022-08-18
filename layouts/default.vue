<template>
  <v-app dark>
    <v-navigation-drawer
      v-model="drawer"
      :mini-variant="miniVariant"
      :clipped="clipped"
      fixed
      app
    >
      <v-list>

        <v-btn
          left
          block
          depressed
          elevation="2"
          plain
          raised
          to="/"
        >
          <v-icon>
            {{ icons.mdiHomeOutline }}
          </v-icon>
          <div style="padding-left: 10px">Главная</div>
        </v-btn>

        <v-btn
          block
          depressed
          elevation="2"
          plain
          raised
          to="/login"
        >
          <v-icon>
            {{ icons.mdiAccountOutline }}
          </v-icon>
          <div style="padding-left: 10px">Авторизация</div>

        </v-btn>


      </v-list>
    </v-navigation-drawer>
    <v-app-bar
      :clipped-left="clipped"
      fixed
      app
    >
      <v-app-bar-nav-icon @click.stop="drawer = !drawer"/>

      <v-btn
        icon
        @click.stop="clipped = !clipped"
      >
        <v-icon>mdi-application</v-icon>
      </v-btn>

      <v-toolbar-title v-text="title"/>
      <v-spacer/>
      <v-spacer/>
      <v-spacer/>
      <v-spacer/>
    </v-app-bar>
    <v-main>
      <v-container>
        <Nuxt/>
      </v-container>
    </v-main>

    <v-footer
      :absolute="!fixed"
      app
    >
      <span>&copy; {{ new Date().getFullYear() }}</span>
    </v-footer>
  </v-app>
</template>

<script>
import {mdiHomeOutline} from '@mdi/js';
import { mdiAccountOutline } from '@mdi/js';

export default {
  name: 'DefaultLayout',
  data() {
    return {
      clipped: false,
      drawer: false,
      fixed: false,

      miniVariant: false,
      right: true,
      rightDrawer: false,
      title: 'Vuetify.js',
      icons: {
        mdiHomeOutline,
        mdiAccountOutline
      }
    }
  }
}
</script>
