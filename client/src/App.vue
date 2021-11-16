// Aufagbe 4
<template>
  <v-app>
    <!-- NAVBAR -->
    <v-app-bar class="grey lighten-5" height="150" app>
      <!-- LOGO -->
      <img
        class="mx-2"
        src="https://sportsbar-happyland.at/wp-content/uploads/2017/01/sportsbar_Happyland_Klosterneuburg.png"
        style="height:100px;"
      />

      <!-- SLOGAN -->
      <span
        class="text-truncate text-h4 black--text darken-1"
        style="font-family: Poppins"
        >Viel Bewegung regt auch den Appetit an</span
      >

      <!-- Damit die Buttons aussen sind -->
      <v-spacer></v-spacer>safdsad

      <!-- BEI NORMALER GRÖSSE LG+ -->
      <v-btn
        class="ma-3 hidden-md-and-down"
        link
        v-for="i in links"
        :key="i.name"
        :to="i.route"
        active-class="orange darken-1--text lighten-2"
      >
        {{ i.name }}
      </v-btn>

      <!-- BEI KLEINER ANZEIGE AB MD -->
      <v-app-bar-nav-icon
        @click="sz = !sz"
        class="orange darken-1--text lighten 3 d-lg-none"
      ></v-app-bar-nav-icon>
    </v-app-bar>

    <!-- MENU -->
    <v-navigation-drawer
      app
      hide-overlay
      right
      disable-resize-watcher
      class="mr-0 d-lg-none"
      v-model="sz"
    >
      <v-btn text @click="sz = false">Close</v-btn>
      <v-list-item-group class="hidden-lg-and-up">
        <v-list-item
          link
          v-for="i in links"
          :key="i.name"
          :to="i.route"
          active-class="orange darken-1--text lighten-2"
          >{{ i.name }}</v-list-item
        >
      </v-list-item-group>
    </v-navigation-drawer>

    <v-main>
      <h1>Team</h1>

      <p class="text-justify">
        Lorem ipsum dolor sit amet, consetetur sadipscing elitr, sed diam nonumy
        eirmod tempor invidunt ut labore et dolore magna aliquyam erat, sed diam
        voluptua. At vero eos et accusam et justo duo dolores et ea rebum. Stet
        clita kasd gubergren, no sea takimata sanctus est Lorem ipsum dolor sit
        amet. Lorem ipsum dolor sit amet, consetetur sadipscing elitr, sed diam
        nonumy eirmod tempor invidunt ut labore et dolore magna aliquyam erat,
        sed diam voluptua. At vero eos et accusam et justo duo dolores et ea
        rebum. Stet clita kasd gubergren, no sea takimata sanctus est Lorem
        ipsum dolor sit amet.
      </p>
    </v-main>
  </v-app>
</template>

<script>
export default {
  name: 'App',

  data: () => ({
    sz: false,
    links: [
      { name: 'Home', route: '/' },
      { name: 'About', route: '/about' },
      { name: 'Speisekarte', route: '/speisekarte' },
      { name: 'Team', route: '/team' },
    ],
  }),
};
</script>
