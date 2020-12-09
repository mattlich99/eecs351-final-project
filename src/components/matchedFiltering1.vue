<template>
  <v-container
    ><v-row no-gutters class="text-h6 font-weight-bold"
      >Matched Filtering Try #1</v-row
    >
    <v-row no-gutters justify="center">
      <div class="mt-6 text-justify" style="font-size: 17px">
        <p>
          The first method we used to identify the drum components was matched
          filtering. What we effectively determined with this algorithm was how
          “close” our input signal was to all our reference signals, by
          comparing each row in the figure below with every column and
          generating a corresponding "quality factor" to each comparison. The
          closer to 1 the value was, the more closely the input signal resembled
          the reference signal. The further away from 1 (either above or below
          it), the more different the signals are, so we could then more likely
          know that our input signal was not that drum component.
        </p>

        <p>
          The algorithm works by first introducing a scaling factor that
          mitigates any volume difference between the signals so that that has
          no effect on our comparison. It then performs two rounds of match
          filtering, the first by convolving a.) a known reference signal with
          itself, and the second by convolving b.) an unknown input signal with
          that same known reference signal. It then compares the resulting
          values from these two matched filtering processes, and that comparison
          generates the quality factor mentioned above. Note that below we have
          used some of individual instrument files as our known reference
          signals, but in our final algorithm the reference signals we used were
          the four averaged signals we discussed above. As we can see, when our
          unknown signal and known signal are the same (i.e. we are comparing a
          signal to itself), our result is 1, shown by the diagonal of the
          matrix.
        </p>

        <p>
          Since we compared each input signal to every reference signal, we had
          multiple quality factors for each one. To detect which drum component
          the input signal actually was, we were originally (and incorrectly)
          taking the minimum value of each column (i.e. the minimum quality
          factor). We were viewing this value as the minimum percent difference
          (which made sense to us because the reference signal with the lowest
          difference would mean that our input signal was closest to that,
          indicating that our input signal was that drum component).
        </p>
        <p>
          However, this process didn't give very accurate results, as the
          indicator of similarity between two signals was how close their
          quality factor was to 1. So what we were doing with this minimum value
          computation was determining the minimum quality factor, which
          realistically meant nothing, when in reality we needed to compute the
          distance that each quality factor was from 1, and then take the
          minimum of those values. Therefore, we had pretty inaccurate results
          and could only identify the correct drum component 30% of the time. To
          improve this accuracy, we used a low pass filter on the snare and kick
          drum average filter to obtain more accurate data specific to those
          instruments. The reason why the low pass filter would yield more
          accurate data for the snare and kick drums is because both of those
          drum kit components operate on a lower frequency spectrum than the
          other instruments. Using the low pass filter on the test signal
          alleviates high frequency noise that leads less accurate data when
          compared to the snare and the kick drum. Including this filter
          increased our overall accuracy to around 40%. However, this was still
          too low for our liking, leading us to try using cross correlation
          (described in the next section) before we went back to a revised
          version of matched filtering.
        </p>
      </div>
    </v-row>
    <v-btn
      color="red lighten-2"
      dark
      :ripple="false"
      class="mt-1 mb-10"
      @click="dialog = true"
    >
      What is Matched Filtering?
    </v-btn>
    <div class="d-flex flex-column align-center mb-8 mt-2">
      <v-img max-width="100%" src="../assets/MatchedFilter1.png"></v-img>
      <div style="font-size: 14px">
        <i>
          Figure 3: Similarity of different audio files (the closer to 1, the
          more similar).</i
        >
      </div>
    </div>

    <v-dialog v-model="dialog" max-width="650px"
      ><v-card
        ><v-card-title>Matched Filtering</v-card-title>

        <v-card-text
          >Match filtering is the process of convolving a known signal with a
          noisy or unknown sample in order to increase the sound to noise ratio
          of the known signal to the noise within the unknown signal. The
          convolution of the known signal with the noisy or unknown sample would
          amplify the known signal within the noise if it is present.
        </v-card-text></v-card
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
