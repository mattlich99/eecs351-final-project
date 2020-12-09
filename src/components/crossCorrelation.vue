<template>
  <v-container
    ><v-row no-gutters class="text-h6 font-weight-bold"
      >Cross Correlation
    </v-row>
    <v-row no-gutters>
      <div class="mt-6 text-justify" style="font-size: 17px">
        <p>
          Because cross correlation is a way to measure the similarity of two
          signals, we tried to calculate the cross correlation of a known audio
          file with an unknown audio file to see what instrument it is closest
          to. Interestingly, when the audio from an instrument is cross
          correlated with different audio from the same instrument, the result
          is more or less symmetrical about 0, as shown in the plots on the
          left. This is because the cross correlation of a signal with itself is
          always symmetrical, so the more similar two signals are, the more
          symmetrical they are.
        </p>
        <p>
          When two different instruments are cross correlated, the result is
          very asymmetrical about 0, as shown in the plots below. We tried to
          use this as a test to see what instrument is being played, but
          unfortunately, when multiple instruments are being played
          simultaneously, the pattern no longer holds. If we had more time we
          could create code that would first split the incoming signal into
          different instruments and then work on identifying the split up
          signals. Because of this issue, we returned to matched filtering to
          try and increase the accuracy of our first attempt.<br />*If you'd
          like to see more cross correlation data, see our
          <router-link to="/data"> More Data</router-link> page.
        </p>
      </div>
      <v-btn
        color="red lighten-2"
        dark
        :ripple="false"
        class="mt-1 mb-10"
        @click="dialog = true"
      >
        What is Cross Correlation?
      </v-btn></v-row
    >
    <v-row
      no-gutters
      class="d-flex justify-lg-space-between justify-lg-center mt-5 mb-6"
    >
      <div>
        <v-img max-width="500px" src="../assets/CrossCorrelation1.png"></v-img>
        <div
          class="text-center text-lg-left mt-2"
          style="width: 88%; font-size: 14px"
        >
          <i> Figure 4: Cross Correlation of two Crash Cympbals.</i>
        </div>
      </div>
      <div>
        <v-img
          class="flex-grow-0"
          max-width="500px"
          src="../assets/CrossCorrelation2.png"
        ></v-img>
        <div
          class="text-center text-lg-left mt-2"
          style="width: 88%; font-size: 14px"
        >
          <i> Figure 5: Cross Correlation of Crash Cympbal & High Hat.</i>
        </div>
      </div></v-row
    >

    <v-dialog v-model="dialog" max-width="650px"
      ><v-card
        ><v-card-title>Cross Correlation</v-card-title>

        <v-card-text
          >The cross correlation between two signals results in a plot that is
          symmetrical when the two signals are very similar, perfectly
          symmetrical when the signals are exactly the same, and asymmetrical
          when the two signals are very different. It is possible to determine
          how similar any two signals are by measuring how symmetrical the cross
          correlation is.</v-card-text
        ></v-card
      >
    </v-dialog>
  </v-container>
</template>

<script>
export default {
  data: () => ({
    dialog: false
  })
}
</script>

<style scoped>
* {
  /* border: 1px solid black; */
}
</style>
