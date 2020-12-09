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
          'A snare drum when played has a low sharp sound. This low sound is represented in the fourier domain by large magnitudes in the lower frequency range, while the sharpness of the sound is represented in the mid range frequencies. This is seen in the plots of different snare drum samples as a large spike at low frequencies and with a wide range of small magnitudes throughout the mid frequency range entering into the high frequency range.  '
      },
      {
        title: 'Averaged Snare Drum Reference Sample',
        name: 'Snare_Average.jpg',
        text:
          'Taking many different samples of a snare drum and combining them into a single average results in a general representation of what a snare drum sample would look like when plotted in the fourier domain. The average signal maintains the characteristics of the individual plots, notably the large spike visible in the low frequency range, and a smear of various magnitudes in the mid range frequencies and entering into the high frequency range.'
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
          'The Kick Drum is personified by three major characteristics, all of which are displayed in the given samples. Firstly, the bass drum operates on a lower frequency range than any of the other given instruments. Secondly, the magnitude of the kick drum is much higher at the lower frequencies than the other instruments. Lastly, there is less echo than the other drum kit components, meaning that the magnitude of the fast fourier transform of the kick drum is much less at higher frequencies than the other bass drum components. All of these characteristics lead to possible methods of identifying the kick drum, either by its unique shape (average filter) and/or a low pass filter. Each of these methods will be explained in more detail in the later sections.'
      },
      {
        title: 'Averaged Kick Drum Reference Sample',
        name: 'Kick_Average.png',
        text:
          ' As the viewer can see, we expect the magnitude of the bass drum to be larger. Therefore, we now know that the averaging algorithm may not give us exact expected results when placed in the match filter. Specifically for the bass drum comes the question of how useful is an average filter when identifying this instrument. Since the bass drum is characterized by a large impulse at low frequencies, we can put our test signal through a low pass filter and see if the signal passes through a threshold. In our implementation of the algorithm, we will explore using a low pass filter on the average filter result. '
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
    }
  }
}
</script>

<style scoped>
* {
  /* border: 1px solid black; */
}
</style>
