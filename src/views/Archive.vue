<template>
  <v-container>
    <div class="flex-column justify-center align-center">
      <div class="text-center mt-8 mb-15">
        <h1 class="text-center mb-5">Project Gantt Chart</h1>
        <div class="d-flex justify-space-around align-center">
          <v-img src="../assets/ganttChart.png"></v-img>
        </div>
      </div>

      <v-divider color="black"></v-divider>
      <div class="text-center mt-8 mb-15">
        <h1 class="text-center mb-5">(11/17/2020) Team Progress Report</h1>
        <div class="d-flex justify-space-around align-center">
          <iframe
            width="800"
            height="500"
            src="https://docs.google.com/document/d/e/2PACX-1vRqI5n-Plt6ZcnLC6ws7QlSLqmCyVtjhv43eNxqPcSe_5VB-OaEoBkXoDSqPeyR_i1ozs_XznjwhGKa/pub?embedded=true"
          ></iframe>
        </div>
      </div>

      <v-divider color="black"></v-divider>

      <div class="text-center mt-8 mb-8">
        <h1 class="text-center mb-5">
          (11/6/2020) Initial Team Report and Video
        </h1>
        <div class="d-flex justify-center align-center">
          <iframe
            width="600"
            height="400"
            src="https://www.youtube.com/embed/55DcOdTSbp0"
            frameborder="0"
            allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture"
            allowfullscreen
          ></iframe>
        </div>
        <div class="d-flex justify-center align-center py-10">
          <iframe
            width="800"
            height="500"
            src="https://docs.google.com/document/d/e/2PACX-1vTDP8lL0RMcpOdj_5ojnEc-VR02PWb9hASGOUKgE8y1t6Efw4I6Dwex_YkpMmOitMoiq4RNkS0u77aG/pub?embedded=true"
          ></iframe>
        </div>
        <v-divider color="black"></v-divider>
      </div>

      <div class="text-h4 mb-4">Sources</div>
      <ul>
        <li>
          <a
            style="text-decoration: none"
            href="https://sound.media.mit.edu/Papers/kdm-phdthesis.pdf"
            target="_blank"
            >MIT Audio DSP Report</a
          >
        </li>
        <li>
          <a
            style="text-decoration: none"
            href="https://okgo.net/"
            target="_blank"
          >
            OKGO</a
          >
        </li>
      </ul>
    </div>
  </v-container>
</template>
<script>
export default {
  metaInfo: {
    title: 'Archive'
  }
}
</script>
<style scoped>
* {
  /* border: 1px solid black; */
}
</style>
