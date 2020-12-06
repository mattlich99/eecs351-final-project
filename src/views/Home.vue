<template>
  <div>
    <Graphic />
    <div class="blue lighten-4">
      <Intro />
    </div>
    <div class="white">
      <ReportDataSection />
    </div>

    <!--<div> - Large Title and Grpahic</div>
  <v-divider color="black" ></v-divider>
  <div> - Section for good broad overview of your problem, so that the rest of the world (not just me) can quickly understand what you wanted to do</div>
  <v-divider color="black" ></v-divider>
  <div> - Section for Progress as of 11/16/2020 One of the initial things we realized when starting this project was that we needed a single matlab file that could process all of our data and return the information we wanted. In the beginning we were all working individually and all had our own matlab files we were using, but we quickly realized that in order for there to be any uniformity between the different results we were finding we needed everyone to be on the same page and producing the same outputs from their input data. This is the reason why we built matlab functions and then distributed those to the group for the purpose of processing our data in a way that we all understood, allowing us to quickly and efficiently explain what we have found and understand what each other are working on. <br><br>
This being said, one of our biggest challenges has been uniform testing for each drum kit component. Since each component has different qualities unique to each instrument, we know that using the average filter for all of the instruments, although convenient for uniform testing, may not be the best course of action moving forward. As described in the above graph sections, some of the instruments may benefit from different forms of filtering.<br><br>
</div>
<v-divider color="black" ></v-divider>
  <div> - Section for Plan over next few weeks (Gantt chart?) at least three tasks you need to do over the next three weeks until the project is due.</div>


-->
  </div>
</template>

<script>
import Graphic from '../components/Graphic.vue'
import Intro from '../components/Intro.vue'
import ReportDataSection from '../components/ReportDataSection.vue'

export default {
  name: 'Home',

  components: {
    Graphic,
    Intro,
    ReportDataSection
  }
}
</script>
