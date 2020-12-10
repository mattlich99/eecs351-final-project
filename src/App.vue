<template>
  <v-app>
    <v-app-bar app color="primary" dark flat>
      <NavBar />
    </v-app-bar>

    <v-main>
      <router-view></router-view>
    </v-main>

    <v-footer color="primary" class="mt-8">
      <Footer />
    </v-footer>
  </v-app>
</template>

<script>
import Footer from './components/Footer'
import NavBar from './components/NavBar'
require('./assets/ECEHeader.png')

export default {
  metaInfo: {
    title: 'EECS 351 Final Project | Drum Component Identification',
    // if no subcomponents specify a metaInfo.title, this title will be used
    titleTemplate: '%s | Drum Component Identification',
    link: [
      { rel: 'favicon', href: '../src/assets/images/slide-logos/favicon.ico' }
    ]
  },
  name: 'App',

  components: {
    Footer,
    NavBar
  }
}
</script>
