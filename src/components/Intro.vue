<template>
  <v-container
    ><v-row class="justify-center font-weight-bold text-h4">Introduction</v-row>
    <v-row
      >Introduction: This report will detail our overall project, process, and
      results. It will include several sections that will explain the problem,
      theory, the unique digital signal processing tools used, as well as our
      algorithm and results. Our goal is to recognize which instrument is
      playing during a mixed drum stem. Problem: The general problem we are
      trying to solve is the lack of an ability to extract source
      instrument-tracks from a mixed track. This is notoriously difficult, and
      from the main paper we cited for this project, strong results require
      algorithms and tools that are outside of the scope of this class. However,
      the drums in particular have characteristics that make source extraction
      somewhat easier than other instruments. Specifically, some drum kit parts
      operate on a lower frequency or have differing “shapes” in the frequency
      domain (See Data Section) than other common instruments. The key to
      solving this problem for the drum kit specifically is to characterize the
      drum components by its qualitative and quantitative characteristics, then
      compare the quantitative aspects of one instrument to an entire track’s
      quantitative aspects. In more technical terms, this means comparing the
      frequency spectrum of snippets from a known signal and an unknown mixed
      signal. Goal: As stated in the introduction, our goal is to which
      instrument is playing during a mixed drum stem. This goal has been paired
      down significantly since the project’s inception. The goal has undergone
      changes as follows. Initially, our goal was to identify multiple drum kit
      components within a mixed track. This goal was set at the beginning of the
      project with stretch goals like extending our implementation to other
      instruments in mind. However, after realizing that our current
      implementation of match filtering was not sufficient (in greater detail in
      the match filtering section), we decided to switch to
    </v-row>
  </v-container>
</template>
