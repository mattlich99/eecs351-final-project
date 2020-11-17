<template>
<v-container>
<div class="d-flex align-center">
        <router-link to="/">
        <div class="d-flex">
        <v-img
          alt="Drums Logo"
          class="shrink mr-2"
          contain
          src="../assets/Drums.png"
          
          width="60"
        
        />
        <div class="d-flex align-center">
        <h2 class="home-title">EECS 351 Final Project</h2>
        </div>
        </div>
        </router-link>

      <v-spacer></v-spacer>
            <v-btn
        text
        to="/data"
      >
        <span >Data</span>
       
      </v-btn>
       <v-btn
        text
        to="/what-we-learned"
      >
        <span >What we Learned</span>
       
      </v-btn>

<v-btn
        
        text
        to="/team"
      >
        <span >Our Team</span>
   
      </v-btn>


      <v-btn
        
        text
        to="/archive"
      >
        <span >Archive</span>
   
      </v-btn>

     
      
      
      
   
  
      </div>



      </v-container>
      </template>

      <style scoped>
.home-title {
  color:white;
  font-weight: 200;
}
        </style>