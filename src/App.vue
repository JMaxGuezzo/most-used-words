<template>
  <v-app>
    <v-app-bar>
      <v-toolbar-title>
        Most Used Words
      </v-toolbar-title>

    </v-app-bar>
    <v-main>
      <the-home />
    </v-main>
  </v-app>
</template>

<script>
import TheHome from './components/TheHome.vue'

export default {
  name: 'App',

  components: {
    TheHome,
  },
}
</script>
