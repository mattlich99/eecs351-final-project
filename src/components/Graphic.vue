<template>
  <div>
    <v-img height="100vh" src="../assets/HomeGraphic.jpg"
      ><v-overlay
        absolute
        :style="fontSize"
        class="text-center font-weight-bold"
      >
        Drum Component Identification</v-overlay
      ></v-img
    >
  </div>
</template>

<script>
export default {
  computed: {
    fontSize() {
      switch (this.$vuetify.breakpoint.name) {
        case 'xs':
          return 'font-size:40px; line-height:60px'
        case 'sm':
          return 'font-size:60px; line-height:80px'

        default:
          return 'font-size:90px;line-height:120px'
      }
    }
  }
}
</script>
