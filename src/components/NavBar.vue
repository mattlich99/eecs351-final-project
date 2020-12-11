<template>
  <v-container>
    <div class="d-flex align-center">
      <a href="https://eecs351-final-project.web.app/">
        <div class="d-flex">
          <v-img
            alt="Drums Logo"
            class="shrink mr-2"
            src="../assets/Drums.png"
            width="58"
          />
          <div class="d-flex align-center">
            <div
              class="white--text font-weight-regular text-subtitle-2 text-sm-h5"
            >
              EECS 351 Final Project
            </div>
          </div>
        </div>
      </a>

      <v-spacer></v-spacer>
      <v-menu open-on-click bottom offset-y>
        <template v-slot:activator="{ on, attrs }">
          <v-btn
            color="primary"
            dark
            v-bind="attrs"
            depressed
            class="hidden-md-and-down"
            :ripple="false"
            v-on="on"
          >
            Project Overview
          </v-btn>
        </template>

        <v-list class="pa-0">
          <v-list-item
            v-for="(item, index) in items"
            :key="index"
            :to="item.to"
          >
            <v-list-item-title>{{ item.title }}</v-list-item-title>
          </v-list-item>
        </v-list>
      </v-menu>

      <v-btn
        text
        to="/data"
        class="hidden-md-and-down"
        :ripple="false"
        @click.native="scrollToTop"
      >
        <span>More Data</span>
      </v-btn>
      <a
        href="https://drive.google.com/file/d/14S-Mbrtf1KDl4rEL7fcUKQaQLkugka1t/view?usp=sharing"
        target="_blank"
      >
        <v-btn text class="hidden-md-and-down" :ripple="false">
          <span>Code</span>
        </v-btn></a
      >
      <v-btn
        text
        to="/team"
        class="hidden-md-and-down"
        :ripple="false"
        @click.native="scrollToTop"
      >
        <span>Our Team</span>
      </v-btn>

      <v-btn
        text
        to="/archive"
        class="hidden-md-and-down"
        :ripple="false"
        @click.native="scrollToTop"
      >
        <span>Archive</span>
      </v-btn>

      <!--START MOBILE LIST-->
      <v-menu open-on-click bottom offset-y min-width="100%" tile>
        <template v-slot:activator="{ on, attrs }">
          <v-btn
            color="primary"
            v-bind="attrs"
            icon
            x-large
            class="hidden-lg-and-up"
            v-on="on"
          >
            <v-icon light color="white"> mdi-menu </v-icon>
          </v-btn>
        </template>
        <v-list class="text-center py-0">
          <v-list-item to="/">
            <v-list-item-title>Project Overview</v-list-item-title>
          </v-list-item>
          <v-list-item to="/data">
            <v-list-item-title> More Data</v-list-item-title>
          </v-list-item>
          <a
            href="https://drive.google.com/file/d/14S-Mbrtf1KDl4rEL7fcUKQaQLkugka1t/view?usp=sharing"
            target="_blank"
            style="text-decoration: none"
          >
            <v-list-item>
              <v-list-item-title>Code</v-list-item-title>
            </v-list-item></a
          >
          <v-list-item to="/team">
            <v-list-item-title>Our Team</v-list-item-title>
          </v-list-item>
          <v-list-item to="/archive">
            <v-list-item-title>Archive</v-list-item-title>
          </v-list-item>
        </v-list>
      </v-menu>
    </div>
  </v-container>
</template>

<script>
import smoothscroll from 'smoothscroll-polyfill'
export default {
  data: () => ({
    items: [
      { title: 'Introduction', to: '/#intro' },
      { title: 'Creating Reference Samples', to: '/#reference-samples' },
      { title: 'Identification Algorithms', to: '/#algorithms' },
      { title: 'What We Learned', to: '/#learned' },
      { title: 'Conclusion', to: '/#conclusion' }
    ]
  }),
  methods: {
    scrollToTop() {
      smoothscroll.polyfill()
      window.scrollTo({ top: 0, behavior: 'smooth' })
    }
  }
}
</script>

<style scoped>
* {
  /* border: 1px solid black; */
}
</style>
