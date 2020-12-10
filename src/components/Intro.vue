<template>
  <div>
    <p>
      The goal of this project was to identify the drum kit components playing
      during a mixed drum stem. A drum stem is a track of a song that only
      includes the drum kit output. From this output, we sought to identify the
      kick/bass drum, the snare drum, the crash cymbal, and the hi-hat.
    </p>
    <p>
      The general problem we tried to solve is the lack of an ability to extract
      source instrument-tracks from a mixed track. This is notoriously
      difficult, and from the main
      <a
        style="text-decoration: none"
        href="https://sound.media.mit.edu/Papers/kdm-phdthesis.pdf"
        target="_blank"
        >MIT paper</a
      >
      we cited for this project, solid results require algorithms and tools that
      are outside of the scope of EECS 351. However, the drums in particular
      have characteristics that make source extraction somewhat easier than
      other instruments. Specifically, some drum kit parts operate on a lower
      frequency or have differing “shapes” in the frequency domain than other
      common instruments. The key to solving this problem for the drum kit
      specifically is to characterize the drum components by their qualitative
      and quantitative characteristics, then compare the quantitative aspects of
      one instrument to an entire track’s quantitative aspects. In more
      technical terms, this means comparing the frequency spectrum of snippets
      from the known reference signal of each drum component to an unknown mixed
      signal containing all four components.
    </p>
  </div>
</template>
