
<template>
  <div >
    <p>3 plots that you think really demonstrate some of the interesting aspects of your project. Please describe all three plots in detail and what you did to get them. If you are using multiple data types, be sure to include ALL types in at least one of your plots.
</p>

<div class="d-flex space-around">
<DataPlot/>
<DataPlot/>
<DataPlot/>
</div>




    
  </div>
</template>

<script>
import DataPlot from '../components/Data/DataPlot';

export default {
  name: 'Data',

  components: {
    DataPlot
  }

 
};
</script>