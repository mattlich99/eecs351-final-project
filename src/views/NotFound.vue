<template>
  <v-container>
    <div class="center">
      <h1>The page you are looking for can't be found.</h1>
      Click <router-link to="/">here</router-link> to return to our homepage. If
      you got to this page by clicking a link, please email the web designer at
      mattlich@umich.edu.
    </div>
  </v-container>
</template>

<script>
export default {
  metaInfo: {
    title: 'Page not found | Drum Component Identification'
    // if no subcomponents specify a metaInfo.title, this title will be used
  }
}
</script>
