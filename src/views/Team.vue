
<template>
  <v-container>
    <h1>Our Squad</h1>
    <Profile/>
     <Profile/>
      <Profile/>
       <Profile/>
  </v-container>
</template>

<script>
  import Profile from '../components/Profile';
export default {


  name: 'Team',

  components: {
  Profile
  }
 
};
</script>
