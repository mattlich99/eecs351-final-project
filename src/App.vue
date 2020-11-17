<template>
  <v-app>
    <v-app-bar
      app
      color="primary"
      dark
    >
      <NavBar/>
    </v-app-bar>

    <v-main>
      <router-view></router-view>
    </v-main>

    <v-footer dark>
    
        <Footer/>
      
      </v-footer>
  </v-app>
</template>

<script>
import Footer from './components/Footer';
import NavBar from './components/NavBar';

export default {
  name: 'App',

  components: {
    Footer,
    NavBar
  }

 
};
</script>

