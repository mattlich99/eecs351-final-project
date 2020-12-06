<template>
  <v-container>
    <div class="d-flex align-center">
      <router-link to="/">
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
      </router-link>

      <v-spacer></v-spacer>
      <v-menu open-on-hover bottom offset-y>
        <template v-slot:activator="{ on, attrs }">
          <v-btn
            color="primary"
            dark
            v-bind="attrs"
            depressed
            class="hidden-sm-and-down"
            v-on="on"
          >
            Final Report
          </v-btn>
        </template>

        <v-list>
          <v-list-item v-for="(item, index) in items" :key="index">
            <v-list-item-title>{{ item.title }}</v-list-item-title>
          </v-list-item>
        </v-list>
      </v-menu>

      <v-btn text to="/data" class="hidden-sm-and-down">
        <span>Data</span>
      </v-btn>
      <v-btn text to="/team" class="hidden-sm-and-down">
        <span>Our Team</span>
      </v-btn>

      <v-btn text to="/archive" class="hidden-sm-and-down">
        <span>Archive</span>
      </v-btn>

      <v-menu open-on-click bottom offset-y>
        <template v-slot:activator="{ on, attrs }">
          <v-btn
            color="primary"
            v-bind="attrs"
            icon
            class="hidden-md-and-up"
            v-on="on"
          >
            <v-icon light color="white"> mdi-menu </v-icon>
          </v-btn>
        </template>
        <v-list>
          <v-list-item to="/">
            <v-list-item-title>Final Report</v-list-item-title>
          </v-list-item>
          <v-list-item to="/data">
            <v-list-item-title>Data</v-list-item-title>
          </v-list-item>
          <v-list-item to="/team">
            <v-list-item-title>Team</v-list-item-title>
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
export default {
  data: () => ({
    items: [
      { title: 'Introduction' },
      { title: 'Click Me' },
      { title: 'Click Me' },
      { title: 'What We Learned' }
    ]
  })
}
</script>
