<template>
  <v-container>
    <v-row no-gutters class="text-h6 font-weight-bold"
      >Producing Averaged Reference Signal</v-row
    >
    <v-row justify="center"
      ><v-col
        cols="9"
        lg="6"
        class="d-flex justify-center flex-column align-center"
      >
        <div class="mt-5" style="font-size: 17px">
          <p>
            The following plot is the averaged snare drum reference sample,
            created from the 8 samples plotted above. The function that created
            these can be found in our
            <a
              href="https://drive.google.com/file/d/14S-Mbrtf1KDl4rEL7fcUKQaQLkugka1t/view?usp=sharing"
              target="_blank"
              >code page</a
            >
            along with the rest of the algorithms we used for this project.
            Since MATLAB is unable to add arrays of different lengths, our
            averager function made use of MATLAB's native "imresize" function,
            which takes each signal in the array and resizes it to the size of
            the smallest signal while minimizing data loss in the process.
          </p>
          The reason we averaged these 8 signals is because we wanted to have a
          good reference to ideally use in any type of track, since there are so
          many ways a snare can sound, a bass drum can sound, etc. depending on
          the material it’s made with, it’s tightness, etc. However, we saw that
          when we hit around 8-10 samples in our average, we hit sort of an
          “asymptotic addition”, where adding more drum samples didn’t really
          affect our resulting average sample, so we knew we had a good, broad
          reference signal to use at that point. As mentioned above, each
          instrument has distinct features, and here we can see that those of
          the snare are maintained: a high initial pulse, most of the frequency
          in the mid-range, and lingering frequencies out through the 3kHz
          range. This sample served as our snare drum reference in the
          algorithms employed below.
        </div> </v-col
      ><v-col class="d-flex flex-column align-center align-lg-end">
        <v-img
          max-width="500px"
          class="flex-grow-0"
          src="../assets/Snare_Average.jpg"
        ></v-img>
        <div
          class="text-center text-lg-left"
          style="width: 80%; font-size: 14px"
        >
          <i> Figure 2: Averaged Snare Drum Reference Sample </i>
        </div>
      </v-col></v-row
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
