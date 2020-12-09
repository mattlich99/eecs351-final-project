<template>
  <v-container>
    <v-row no-gutters class="text-h6 font-weight-bold"
      >Gathering Signals in the Fourier Domain</v-row
    >
    <v-row justify="center"
      ><v-col
        cols="9"
        lg="6"
        class="d-flex justify-stretch flex-column align-lg-start align-center"
      >
        <div class="mt-6 text-justify" style="font-size: 17px">
          As mentioned above, we first started by choosing 4 components of the
          drum kit and used the FFT to view them in the frequency domain, as
          seen to the right with the snare drum's data (for the rest of the
          report, we will be referencing the snare data for brevity; if you'd
          like to see data for the other 3 instruments, please visit the
          <router-link to="/data"> More Data</router-link> page, where the snare
          data is present as well). As we can see in the following subplot,
          there are some key characteristics to the snare drum that we used in
          our identification algorithms to differentiate it from the other drum
          components: a high magnitude initial pulse; most of the frequency in
          the mid-range from about 250Hz-4ooHz; and small magnitude frequencies
          extending from about 900Hz-3kHz (called "wire" frequencies, resulting
          from the lingering vibration of the wires that hold the snare
          together).
        </div>
        <v-btn
          color="red lighten-2"
          dark
          :ripple="false"
          class="mt-5 mb-4"
          @click="dialog = true"
        >
          What is FFT?
        </v-btn></v-col
      ><v-col class="d-flex justify-center justify-lg-end"
        ><div class="d-flex flex-column align-center align-lg-end">
          <v-img max-width="500px" src="../assets/Snare_Sub.jpg"></v-img>
          <div
            class="text-center text-lg-left"
            style="width: 88%; font-size: 14px"
          >
            <i>
              Figure 1: Magnitude FFTs vs. Snare Drum Frequency using eight
              different samples.</i
            >
          </div>
        </div></v-col
      ></v-row
    >

    <v-dialog v-model="dialog" max-width="650px"
      ><v-card
        ><v-card-title>Fast Fourier Transform</v-card-title
        ><v-card-text
          >The Fast Fourier transform (FFT) is a method of signal processing
          that converts a signal from the time domain (seconds) to the frequency
          domain (hertz). It is made out of several discrete fourier transforms
          (DFT). The discrete fourier transform formula is displayed
          below:</v-card-text
        >
        <div style="width: 100%" class="d-flex justify-center">
          <v-img
            class="mb-4"
            max-width="80%"
            src="../assets/FFTFormula.png"
          ></v-img>
        </div>
        <v-card-text
          >This formula takes in each term from the time-based signal (x[n]) and
          “transforms” it to the frequency domain using the W term. Each
          transformed signal is then summed to create the signal in the
          frequency domain.</v-card-text
        ><v-card-text
          >Now why would we change to the frequency domain? It turns out that
          performing convolution on our filters is much easier in the frequency
          domain. </v-card-text
        ><v-card-text
          >Why do we use the fast fourier transform instead of computing several
          discrete fourier transforms? The fast fourier transform is an
          algorithm that is optimized for large amounts of computation, as it
          expects the amount of computation needed before solving the above
          formula. Therefore, it is much more efficient to use the FFT than
          individual DFTs.</v-card-text
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
