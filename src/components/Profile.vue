<template>
  <v-card elevation="5" width="300">
    <v-img
      alt="Drums Logo"
      :src="require('@/assets/' + imageName + '')"
      height="300px"
    />
    <v-card-title>
      <div class="mr-3">{{ Name }}</div>
      <a :href="linkedin" target="_blank"
        ><v-img
          max-width="26px"
          rounded
          src="../assets/linkedin-icon.png"
        ></v-img
      ></a>
    </v-card-title>
    <v-card-subtitle>
      {{ Major_GradYear }}
    </v-card-subtitle>
    <v-card-text>
      {{ Hometown }}
    </v-card-text>
    <v-card-text>
      {{ Bio }}
    </v-card-text>
  </v-card>
</template>

<script>
export default {
  props: {
    Name: {
      type: String,

      default: 'Team Member'
    },

    Major_GradYear: {
      type: String
    },

    Bio: {
      type: String
    },

    Hometown: {
      type: String
    },
    imageName: {
      type: String,
      required: true
    },
    linkedin: {
      type: String,
      required: true
    }
  }
}
</script>
