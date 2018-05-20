---
title: 2018-05-19-frequency domain & time domain
categories:
 - research_study
tags:
 - DFT
---

### frequency domain(F-D) & time domain(T-D)

This is study note of [this page](http://www.doc88.com/p-1476519575199.html).

1. *Definition and difference*

   - two descriptions of signals, two dimensions of the real world (so a single signal in T-D could be interpret into many components in F-D)

   - |                    | T-D                                          | F-D                                                          |
     | :----------------: | :------------------------------------------- | :----------------------------------------------------------- |
     |                    | real                                         | mathematic                                                   |
     | important features | 2 parameters:<br>- time-clock<br>-  risetime | Set of sine functions is<br> - orthogonal and complete<br>- differentiable everywhere |

2. *Connection*

   For discrete signal, F-D and T-D are connected by DTFT or DFT(seasonal).

   **Non-seasonal** signal takes infinite number of sine-curves to interpret. So normally we extend it by **copying itself** and then use **DFT**. Only in this way can the signal be address by computer in F-D.

   DFT can be divided into **real DFT**(corresponding to Amplitude Spectrum, even symmetry) and **imagine DFT**(Phase Spectrum, odd symmetry). And please note that the transform we use (not strictly 1 to 1) is different from the functional transform(1 to 1). 

3. *Corresponding relationship*

   - Time change rate is proportional to frequency spectrum

     --- the rise of time change rate leads to the rise of upper frequency limit

   - Time period is inversely proportional to frequency spectrum

     --- the decrease of time period leads to the increase of high-frequency energy's proportion

   - Pulse width is inversely proportional to frequency spectrum

     --- the decrease of pulse width leads to the wider distribution range of frequency spectrum

4. *Conclusion of the spectrum of seasonal / non-seasonal function*

   |               | seasonal func. | non-seasonal func. |
   | ------------- | -------------- | ------------------ |
   | Domain change | Fourier Series | Fourier Transform  |
   | Spectrum      | discrete       | continuous         |

   *Please note that the negative frequency part in spectrum is meaningless in the real world

5. *Sampling of discrete Fourier transform*

   - Nyquist Theory 

     - sampling frequency should at least twice the signal frequency, as well as being **2^N** 

     -  take each frequency point(the chosen ones) as center, the upper to the lower sideband of every frequency have all the information of the original signal

       ---- so normally, we only take the lower to the upper sideband of **0Hz** as spectrum, and this section could give the ideal original signal when carrying out IFFT

       ---- so a lowpass with bandwidth of the 0Hz-center frequency range could reshow the time-domain signal

       ---- **the more sampling points we have, a more similar time-domain signal we could reshow after IFFT**

    - the longer time we sampling, the higher frequency resolution we will get in spectrum.

       ---- normally, due to real-time processing needs, we could extend the original signal by **adding 0s** at the end of the recorded data to increase **frequency resolution**
