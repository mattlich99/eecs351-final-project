<template>
  <div>
    <Graphic />
    <div id="intro">
      <v-container>
        <v-row no-gutters class="font-weight-bold text-h4 my-4"
          >Introduction</v-row
        ><Intro />
        <v-divider color="black" class="mt-10"></v-divider>
      </v-container>
    </div>

    <div id="reference-samples">
      <v-container>
        <v-row no-gutters class="font-weight-bold text-h4 my-4"
          >Creating Reference Samples</v-row
        ><FFTSamples /> <averageSample class="mt-8" />
        <v-divider color="black" class="mt-10"></v-divider>
      </v-container>
    </div>

    <div id="algorithms">
      <v-container>
        <v-row no-gutters class="font-weight-bold text-h4 my-4"
          >Identification Algorithms</v-row
        ><matchedFiltering1 /><crossCorrelation /><matchedFiltering2 /><v-divider
          color="black"
          class="mt-10"
        ></v-divider>
      </v-container>
    </div>

    <div id="learned">
      <v-container>
        <v-row no-gutters class="font-weight-bold text-h4 my-4"
          >What We Learned</v-row
        >
        <Learned /><v-divider color="black" class="mt-10"></v-divider>
      </v-container>
    </div>

    <div id="conclusion">
      <v-container>
        <v-row no-gutters class="font-weight-bold text-h4 my-4"
          >Conclusion</v-row
        ><Conclusions />
      </v-container>
    </div>
  </div>
</template>

<script>
import Graphic from '../components/Graphic.vue'
import Intro from '../components/Intro.vue'
import FFTSamples from '../components/FFTSamples.vue'
import averageSample from '../components/averageSample.vue'
import matchedFiltering1 from '../components/matchedFiltering1.vue'
import crossCorrelation from '../components/crossCorrelation.vue'
import matchedFiltering2 from '../components/matchedFiltering2.vue'
import Learned from '../components/Learned.vue'
import Conclusions from '../components/Conclusions.vue'

export default {
  name: 'Home',

  components: {
    Graphic,
    Intro,
    FFTSamples,
    averageSample,
    matchedFiltering1,
    crossCorrelation,
    matchedFiltering2,
    Learned,
    Conclusions
  }
}
</script>
