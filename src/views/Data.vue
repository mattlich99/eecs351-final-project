<template>
  <v-container>
    <v-row class="justify-center font-weight-bold text-h4 mt-6"
      ><div>Theory we used</div></v-row
    >
    <v-row class="mb-16 mt-4 justify-space-between">
      <v-dialog
        v-for="(modal, index) in modals"
        :key="index"
        v-model="dialog"
        width="500"
      >
        <template v-slot:activator="{ on, attrs }">
          <v-btn color="red lighten-2" dark v-bind="attrs" v-on="on">
            {{ modal.title }}
          </v-btn>
        </template>

        <v-card>
          <v-card-title class="headline grey lighten-2">
            Privacy Policy
          </v-card-title>

          <v-card-text>
            Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do
            eiusmod tempor incididunt ut labore et dolore magna aliqua. Ut enim
            ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut
            aliquip ex ea commodo consequat. Duis aute irure dolor in
            reprehenderit in voluptate velit esse cillum dolore eu fugiat nulla
            pariatur. Excepteur sint occaecat cupidatat non proident, sunt in
            culpa qui officia deserunt mollit anim id est laborum.
          </v-card-text>

          <v-divider></v-divider>

          <v-card-actions>
            <v-spacer></v-spacer>
            <v-btn color="primary" text @click="dialog = false">
              I accept
            </v-btn>
          </v-card-actions>
        </v-card>
      </v-dialog>
    </v-row>
    <h1 class="text-center">Crash Cymbal Data</h1>

    <div class="flex-column">
      <DataPlot
        :data-title="titles[0]"
        :data-description="descriptions[0]"
        :image-name="images[0]"
      />
      <DataPlot
        :data-title="titles[1]"
        :data-description="descriptions[1]"
        :image-name="images[1]"
      />
      <DataPlot
        :data-title="titles[2]"
        :data-description="descriptions[2]"
        :image-name="images[2]"
        :img-width="1000"
      />
    </div>
  </v-container>
</template>

<script>
import DataPlot from '../components/DataPlot'

export default {
  name: 'Data',

  components: {
    DataPlot
  },

  data: () => ({
    modals: [
      {
        title: 'Fast Fourier Transform'
      },
      {
        title: 'Matched Filtering'
      },
      {
        title: 'Cross Correlation'
      },
      {
        title: 'Difference Percent'
      }
    ],
    titles: [
      'Magnitude FFTs using eight different samples vs. Crash Cymbal Frequency.',

      'Average Magnitude FFT using eight different samples vs Crash Cymbal Frequency',

      'Similarity of different audio files'
    ],
    descriptions: [
      'Plotted above are eight crash cymbals which mostly share the same features. Generally there is the first peak around 500 Hz and then the largest peak is between 3 and 4 kHz. After the peak around 5 kHz, the magnitude decays close to 0 by 18 kHz. CrashCymbal4.wav seems to have been compressed because all its magnitudes above 5 kHz are 0. A song could contain compressed or distorted instruments so it will be interesting to see if our code will be able to identify a compressed instrument’s sound as the original instrument.',

      'The averaged plot of the crash cymbals seems to have lost some of its detail but it is a good representation of all the crash cymbals. The exponential decrease is lost but the peaks are still spaced with a group around 500 Hz and the largest peak is at 3128 Hz. We may end up using the averaged plot to identify some instruments but use the original plots for others depending on how accurate the results are with the different methods.',

      'Our first idea to identify an instrument is to use a matched filter. The match filter consists of multiplying the signal whose instrument we are trying to identify with signals which we know the instrument for in the frequency domain. We can then sum up the answer and compare the summation to the summation of the sum of the original signal times itself. The code adjusts for differences in the magnitudes of the two inputs so changing the volume of the signal will not change the result. This chart shows the similarity measured by by this method of two clips of each instrument. The similarity between two identical audios is 1, and the further from 1 the value, the bigger the difference. The two high hats are the most similar and for every instrument other than the snare drum, the two instruments are more similar than almost every other instrument. Moving forward we will use different methods to compare signals, use different kinds of filters before measuring the similarity of audio, and run the program on larger sets of data.'
    ],
    images: ['CymbalPlots.png', 'AverageCymbal.png', 'MatchFilter.png']
  })
}
</script>
