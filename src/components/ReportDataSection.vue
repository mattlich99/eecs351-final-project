<template>
  <v-container>
    <v-row
      ><v-col
        ><v-img
          max-width="200px"
          src="../assets/AverageCymbal.png"
        ></v-img></v-col
      ><v-col cols="6">
        <div>
          We first started by choosing 4 components of the drum kit and used the
          FFT to view them in the frequency domain, as seen to the right with
          the cymbal data (for the rest of the report, we will be referenceing
          the cymbal data for brevity --> if you'd like to see data for the
          other 3 instruments, please visit the
          <router-link to="/data"> data</router-link> tab).. Averaged 8-10
          samples of each...Lorem ipsum dolor sit amet, consectetur adipiscing
          elit, sed do eiusmod tempor incididunt ut labore et dolore magna
          aliqua. Ut enim ad minim veniam, quis nostrud exercitation ullamco
          laboris nisi ut aliquip ex ea commodo consequat. Duis aute irure dolor
          in reprehenderit in voluptate velit esse cillum dolore eu fugiat nulla
          pariatur. Excepteur sint occaecat cupidatat non proident, sunt in
          culpa qui officia deserunt mollit anim id est laborum.
        </div></v-col
      ></v-row
    >
    <v-row class="justify-center"
      ><v-dialog v-model="dialog" width="500">
        <template v-slot:activator="{ on, attrs }">
          <v-btn color="red lighten-2" dark v-bind="attrs" v-on="on">
            FFT Theory
          </v-btn>
        </template>

        <v-card>
          <v-card-title class="headline grey lighten-2">
            Privacy Policy
          </v-card-title>

          <v-card-text>
            Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do
            eiusmod tempor incididunt ut labore et dolore magna aliqua. Ut enim
            ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut
            aliquip ex ea commodo consequat. Duis aute irure dolor in
            reprehenderit in voluptate velit esse cillum dolore eu fugiat nulla
            pariatur. Excepteur sint occaecat cupidatat non proident, sunt in
            culpa qui officia deserunt mollit anim id est laborum.
          </v-card-text>

          <v-divider></v-divider>

          <v-card-actions>
            <v-spacer></v-spacer>
            <v-btn color="primary" text @click="dialog = false">
              I accept
            </v-btn>
          </v-card-actions>
        </v-card>
      </v-dialog></v-row
    >
  </v-container>
</template>

<style scoped>
* {
  /* border: 1px solid black; */
}
</style>
