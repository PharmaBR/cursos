<template>
  <v-app>
    <v-app-bar app color="orange" dark>
      <div class="d-flex align-center">
        <v-img
          alt="Vuetify Logo"
          class="shrink mr-2"
          contain
          src="http://portal.facesa.com.br/img/facesa_brand.svg"
          transition="scale-transition"
          width="140"
        />
      </div>

      <v-spacer></v-spacer>

      <v-btn href="http://portal.facesa.com.br" target="_blank" text>
        <span class="mr-2">O seu futuro começa AQUI!</span>
        <v-icon>mdi-open-in-new</v-icon>
      </v-btn>
    </v-app-bar>

    <v-content>
      <HelloWorld />
    </v-content>
  </v-app>
</template>

<script>
import HelloWorld from "./components/HelloWorld";

export default {
  name: "App",

  components: {
    HelloWorld
  },

  data: () => ({
    //
  })
};
</script>
