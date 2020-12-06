<template>
  <v-container>
    <h3 class="text-center py-5">{{ dataTitle }}</h3>
    <div class="d-flex justify-center align-center">
      <v-img :max-width="imgWidth" :src="require('@/assets/' + imageName + '')">
      </v-img>
    </div>
    <p class="py-5">{{ dataDescription }}</p>
  </v-container>
</template>

<script>
export default {
  props: {
    dataTitle: {
      type: String,
      required: true
    },

    dataDescription: {
      type: String,
      required: true
    },
    imageName: {
      type: String,
      required: true
    },
    imgWidth: {
      type: Number,
      required: true,
      default: 500
    }
  }
}
</script>
