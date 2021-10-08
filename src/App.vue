<template>
  <v-app>
      <!-- header  -->
    <v-app-bar
      app
      color="primary"
      dark
    >
        <v-btn text href="/ " class="d-flex align-center">
            <v-img
            alt="Vuetify Logo"
            class="shrink mr-2"
            contain
            src="https://cdn.vuetifyjs.com/images/logos/vuetify-logo-dark.png"
            transition="scale-transition"
            width="40"/>
            <h1 style="font-weight:500;">VuetifyStudy</h1>
        </v-btn>

        <v-spacer></v-spacer>

        <v-btn
            href="https://github.com/kibum0405/vue-vuetify"
            target="_blank"
            text>
            <span class="mr-2">Github</span>
            <v-icon>mdi-git</v-icon>
        </v-btn>
    </v-app-bar>

    <v-main>
      <HelloWorld/>
    </v-main>
  </v-app>
</template>

<script>
import HelloWorld from './components/HelloWorld';

export default {
    name: 'App',

    components: {
        HelloWorld,
    },

    methods: {
    },


    data: () => ({
        //
    }),
};
</script>
