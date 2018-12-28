<template>
  <v-app :dark="goDark">
    <v-toolbar dense>
      <v-toolbar-side-icon></v-toolbar-side-icon>

      <v-toolbar-title class="headline text-uppercase">
        <span>Vuetify</span>
        <span class="font-weight-light">MATERIAL DESIGN</span>
      </v-toolbar-title>

      <v-spacer></v-spacer>

      <v-toolbar-items class="hidden-sm-and-down">
        <v-btn flat v-on:click="vueHome()">Vue Home</v-btn>
        <v-btn flat v-on:click="PreparedFiles()">Prepared Files</v-btn>
        <v-btn flat v-on:click="Premier()">Premier</v-btn>
        <v-btn flat href="https://github.com/vuetifyjs/vuetify/releases/latest" target="_blank">
          <span class="mr-2">Latest Release</span>
        </v-btn>
      </v-toolbar-items>
      <v-spacer></v-spacer>

      <v-btn flat icon v-on:click="changeDark()">
        <v-icon class="material-icons">invert_colors</v-icon>
      </v-btn>
    </v-toolbar>

    <keep-alive>
      <component :is="displayComponent"></component>
    </keep-alive>
  </v-app>
</template>

<script>
import HelloWorld from "./components/HelloWorld";
import PreparedFiles from "./components/PreparedFiles";
import Premier from "./components/Premier";
import Entity from "./components/Entity";
import PreparedFilesServer from "./components/PreparedFilesServer";
export default {
  name: "App",
  components: {
    PreparedFiles,
    PreparedFilesServer,
    HelloWorld,
    Premier,
    Entity
  },
  data() {
    return {
      displayComponent: "HelloWorld",
      goDark: false
      //
    };
  },
  methods: {
    vueHome() {
      this.displayComponent = "HelloWorld";
    },
    PreparedFiles() {
      this.displayComponent = "PreparedFilesServer";
    },
    Premier() {
      this.displayComponent = "Entity";
    },
    changeDark() {
      return this.goDark ? (this.goDark = false) : (this.goDark = true);
    }
  }
};
</script>
