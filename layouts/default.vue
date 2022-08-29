<template>
  <v-app dark>
    <v-navigation-drawer
      v-model="drawer"
      :mini-variant="miniVariant"
      :clipped="clipped"
      fixed
      app
    >
      <v-list >

        <v-btn
          block
          depressed
          elevation="2"
          plain
          raised
          to="/"
          :class="$style.red"
        >
          <v-icon>
            {{ icons.mdiHomeOutline }}
          </v-icon>
          <div style="padding-left: 10px" >Главная </div>
          <v-spacer/>

        </v-btn>

        <v-btn
          block
          depressed
          elevation="2"
          plain
          raised
          to="/login"
          :class="$style.red"
        >
          <v-icon>
            {{ icons.mdiAccountOutline }}
          </v-icon>
          <div style="padding-left: 10px">Авторизация</div>
          <v-spacer/>
        </v-btn>

        <v-btn
          block
          depressed
          elevation="2"
          plain
          raised
          to="/orders"
          :class="$style.red"
        >
          <v-icon>
            {{ icons.mdiCartOutline }}
          </v-icon>
          <div style="padding-left: 10px">Заказы</div>
          <v-spacer/>
        </v-btn>

      </v-list>
    </v-navigation-drawer>
    <v-app-bar
      :clipped-left="clipped"
      fixed
      app
      :class="$style.red"
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

<style module>
.red {

  background: linear-gradient(to right, #f5efef, #e7d19d);
  box-shadow: 0.4em 0.4em 5px rgb(231, 209, 157);
  margin-top: 5px;
}

</style>


<script>
import {mdiHomeOutline} from '@mdi/js';
import { mdiAccountOutline } from '@mdi/js';
import { mdiCartOutline } from '@mdi/js';

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
      title: 'Личный кабинет дилера',
      icons: {
        mdiHomeOutline,
        mdiAccountOutline,
        mdiCartOutline
      }
    }
  }
}
</script>
