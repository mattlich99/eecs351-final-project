<template>
  <v-container>
    <h1 class="mt-5 text-decoration-underline">All Drum Component Samples</h1>
    <v-row class="mt-6">
      <v-col
        v-for="(image, index) in subImages"
        :key="index"
        lg="6"
        cols="12"
        class="d-flex align-center flex-column my-5 pa-0"
      >
        <h1 class="text-center text-h5">{{ image.title }}</h1>
        <div class="d-flex align-center align-md-start flex-column">
          <v-img
            :max-width="ImageWidth"
            :src="require('@/assets/' + image.name + '')"
            style="border: 1px solid black; max-height: 375px"
            class="flex-grow-0"
          ></v-img>
          <div style="max-width: 480px" class="mt-3 flex-grow-1 px-3">
            {{ image.text }}
          </div>
        </div>
      </v-col>
    </v-row>
    <h1 class="mt-5 text-decoration-underline">Full Cross Correlation Data</h1>
    <v-row no-gutters class="mt-6 justify-center justify-lg-start"
      ><v-img
        :max-width="correlationWidth"
        src="../assets/fullCrossCorrelation.jpg"
      ></v-img>
    </v-row>
  </v-container>
</template>

<script>
export default {
  name: 'Data',
  data: () => ({
    modals: [
      {
        title: 'Fast Fourier Transform'
      },

      {
        title: 'Cross Correlation'
      },
      {
        title: 'Matched Filtering'
      }
    ],
    subImages: [
      {
        title: 'Snare Drum Samples',
        name: 'Snare_Sub.jpg',
        text:
          ' As we can see in the snare drum samples above, there are some key characteristics to the snare drum that we used in our identification algorithms to differentiate it from the other drum components: a high magnitude initial pulse; most of the frequency in the mid-range from about 250Hz-400Hz; and small magnitude frequencies extending from about 900Hz-3kHz (called "wire" frequencies, resulting from the lingering vibration of the wires that hold the snare together).  '
      },
      {
        title: 'Averaged Snare Drum Reference Sample',
        name: 'Snare_Average.jpg',
        text:
          'Taking many different samples of a snare drum and combining them into a single average results in a general representation of what a snare drum sample would look like when plotted in the fourier domain. The average signal maintains the characteristics of the individual plots: a high initial pulse, most of the frequency in the mid-range, and lingering frequencies out through the 3kHz range.'
      },
      {
        title: 'High Hat Samples',
        name: 'HighHat_Sub.png',
        text:
          'The hi hat creates a very shimmery type of sound that exists in the mid and high range of frequencies. This sound is represented by a large range of magnitudes over a large set of frequencies. This is seen in the plot as a smear in the shape of a hump or gaussian curve of magnitudes over the mid and high range of frequencies.'
      },
      {
        title: 'Averaged High Hat Reference Sample',
        name: 'HighHat_Average.jpg',
        text:
          'Taking many different samples of a hi hat and combining them into a single average results in a representation of what any crash cymbal may look like. The average contains the characteristics of the hi hat, notably the broad range of magnitudes over a large range frequency. The shape created by this, the hump or almost gaussian shape, is what most high hats look like when plotted in the frequency domain.'
      },
      {
        title: 'Kick Drum Samples',
        name: 'Kick_Sub.png',
        text:
          'The Kick Drum is personified by three major characteristics, all of which are displayed in the given samples. Firstly, the bass drum operates on a lower frequency range than any of the other given instruments. Secondly, the magnitude of the kick drum is much higher at the lower frequencies than the other instruments. Lastly, there is less echo than the other drum kit components, meaning that the magnitude of the fast fourier transform of the kick drum is much less at higher frequencies than the other bass drum components. '
      },
      {
        title: 'Averaged Kick Drum Reference Sample',
        name: 'Kick_Average.png',
        text:
          ' When we average all the kick drum samples into a single reference signal, we get a decent representation of what any kick drum may look like. The averaged signal maintains the characteristics of the kick drum: most notably the large, low frequency initial magnitude - which is much larger than the magnitudes of the other 3 drum components - along with a rapid decay into a low magnitude signal for  the rest of the frequency range. '
      },
      {
        title: 'Cymbal Samples',
        name: 'Cymbal_Sub.png',
        text:
          'The crash cymbal has an abrupt, loud, crashing sound.  After the cymbal is hit, its sound lingers for longer than the hi hat.  In the frequency domain, the crash cymbal has relatively low frequency peaks in addition to high frequency peaks.  The peaks occur for very small ranges of frequencies and they tend to be more concentrated at lower frequencies than the hi hat.'
      },
      {
        title: 'Averaged Cymbal Reference Sample',
        name: 'Cymbal_Average.png',
        text:
          'When we average together multiple crash cymbals, the result still has the same general shape as individual crash cymbals but now the peaks are smaller compared to the average magnitude of the signal.  The averaged signal has a much smaller magnitude at higher frequencies than some of the original signals.  The exponential decay of magnitude at higher frequencies is lost.  '
      }
    ]
  }),

  metaInfo: {
    title: 'More Data'
  },
  computed: {
    ImageWidth() {
      switch (this.$vuetify.breakpoint.name) {
        case 'xs':
          return '300px'
        case 'lg':
          return '550px'

        default:
          return '500px'
      }
    },
    correlationWidth() {
      switch (this.$vuetify.breakpoint.name) {
        case 'xs':
          return '310px'
        case 'sm':
          return '550px'
        case 'md':
          return '750px'

        default:
          return '900px'
      }
    }
  }
}
</script>

<style scoped>
* {
  /* border: 1px solid black; */
}
</style>
