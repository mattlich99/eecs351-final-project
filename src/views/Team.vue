
<template>
  <div class="about">
    <h1>Our Squad</h1>
    <Profile/>
     <Profile/>
      <Profile/>
       <Profile/>
  </div>
</template>

<script>
  import Profile from '../components/Team/Profile';
export default {


  name: 'Team',

  components: {
  Profile
  }
 
};
</script>
