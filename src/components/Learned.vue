<template>
  <div>
    <p>
      Throughout this project we as a whole have learned a great deal about how
      difficult it can be to create something from nothing but a theory. In
      creating our algorithm we have discovered solutions to problems we didn’t
      realize existed when we initially began our work. When we began this
      project, everyone was excited, we had high hopes, we knew it would be
      difficult, but we did not know how difficult it would be. We believed
      characteristics of the instruments would be easier to distinguish, that
      each instrument would be clearly different from one another, and that
      their representation in the fourier domain would be a clean stem with only
      a few spikes. However, as displayed in the previous theory and data
      section, this was not the case. We were only able to implement the low
      pass filter for the snare and kick drum, which turned out to be quite
      helpful. The cross correlation algorithm was not able to be used because
      of the existence of other instruments in the same track, and the signal
      envelope did not work with the data that we supplied. However, we were
      surprised to find that even without two signal processing algorithms, we
      were able to obtain such accurate results considering the difficulty of
      the problem. Even so, more can be done to improve the accuracy and speed
      of the algorithm.
    </p>
    <p>
      To improve the accuracy of our algorithm, we could try to split the
      unknown audio up into different instruments first and then try to identify
      the split up instruments. This would allow us to effectively use the cross
      correlation algorithm. Also, if we could gather even more data we could
      have different examples of each instrument such as loose, tight, and in
      between snare drums. Another way to improve the accuracy of the algorithm
      is to apply the signal envelope to the hi hat drum kit component. The
      signal envelope would capture the shape of the hi-hat more accurately than
      the average filter, and could even be used on the other instruments as
      well. Finally, we can continue to improve our accuracy in the following
      way: for each drum component, instead of comparing just that component's
      averaged signal to the inputted test signal, we can rather cycle through
      all of that component's individual samples and compare each of them to the
      inputted test signal. Because each component can have varied sounds
      depending on how it's made/tuned, this would greatly increase our accuracy
      as it would be increasing the range for which we could detect that
      component. For example, if we have 8 snare drum samples of arbitrary sound
      type 1-8, respectively, and average them to get an average sounding sample
      of type 4.5, we may not accurately detect a snare drum with a sound of
      type 1; however, we are almost guaranteed to detect it if we compare it to
      all of the signals, as we would have a snare drum of sound 1 in that
      reference group.
    </p>

    <p>
      In order to increase the speed of the algorithm, we could utilize
      multithreading in order to process multiple samples of the spliced drum
      track at the same time in order to increase data feedback and in turn,
      improve the speed of algorithm development.
    </p>
  </div>
</template>
