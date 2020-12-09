<template>
  <v-container
    ><v-row no-gutters class="text-h6 font-weight-bold"
      >Matched Filtering Try #2</v-row
    >
    <v-row no-gutters justify="center">
      <div class="text-justify" style="font-size: 17px">
        <p>
          The second iteration of the match filtering algorithm uses the
          structure of the initial with some improvements. As mentioned in the
          section detailing our first attempt at matched filtering, our
          algorithm initially calculated the minimum of the "quality factors"
          generated from the comparison between the input signal and the known
          reference signals. This value realistically means nothing, and we
          determined that we actually needed to compute the distance that each
          quality factor was from 1, and then take the minimum of those values.
          After making this change to the algorithm (and keeping the low pass
          filter included, as it still gave us a net positive accuracy
          increase), we saw our component identification accuracy jump
          immensely, as displayed below in the spreadsheet.
        </p>
        <p>
          The given spreadsheet displays combined human and computer-based
          analysis of which drum kit components are being played during the
          song. The columns labeled kick, snare, crash, and hi-hat all represent
          a human analysis of when each instrument was being played during each
          second, utilizing the individual instrument stems to accomplish this.
          The Y in this section tells that the instrument was playing in the
          second-long interval, whereas the N in the section tells that the
          instrument was not playing the second-long interval. The column
          labeled drum track column is also human-analyzed, as we compared our
          algorithm’s output, a matrix with which instrument is playing, to what
          was actually playing from the other four columns. A Y in this section
          affirms that our algorithm was accurate to what was being played,
          whereas an N represents that our algorithm was not accurate to which
          instrument was being played.
        </p>
        <p>
          Overall for the whole drum stem, we got 141 correct predictions out of
          202 seconds of samples. This made for an overall accuracy of 69.8%,
          <i>much</i> better than the 40% we were originally getting on our
          first try with this algorithm. One may notice that there are some
          discrepancies in the data, particularly in sections 69-89, where the
          hi-hat was in fact played, but the drummer used the foot pedal for the
          hi-hat. We did not test for this possibility, which led to some
          incorrect predictions. The section 120-150 is also a source of major
          discrepancies, as the toms, a drum kit component we did not test for,
          was played almost exclusively during this section.
        </p>
      </div>

      <div class="d-flex flex-column align-center mt-4" style="width: 100%">
        <!-- <iframe
          width="80%"
          height="500px"
          src="https://docs.google.com/spreadsheets/d/e/2PACX-1vSMKYurNck8kiGPwjHbj_1wmGpGSIY0KfSmzDyR3_JhPJGzb-Yy1ggudx31zXoaoZ5q54GWo1GG6_-6/pubhtml?widget=true&amp;headers=false"
        ></iframe> -->
        <iframe
          width="80%"
          height="500px"
          src="https://docs.google.com/spreadsheets/d/e/2PACX-1vSMKYurNck8kiGPwjHbj_1wmGpGSIY0KfSmzDyR3_JhPJGzb-Yy1ggudx31zXoaoZ5q54GWo1GG6_-6/pubhtml?gid=0&amp;single=true&amp;widget=true&amp;headers=false"
        ></iframe>

        <i class="mt-2">
          Figure 6: Matched Filtering Try #2 Algorithm Output Analysis.</i
        >
      </div></v-row
    >
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
