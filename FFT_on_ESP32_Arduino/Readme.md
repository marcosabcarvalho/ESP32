I wanted a library for performing FFT on ESP32 on Arduino and extract both the fundamental frequency and the amplitude at that frequency. The most popular library seems to be [arduinoFFT](https://github.com/kosme/arduinoFFT) and it gives excellent results for frequency. However, it is not clear how the magnitude in the output gets translated to amplitude and and therefore I was unable to use it for my application. 

I then came across Robin Scheibler's [library](https://github.com/fakufaku/esp32-fft), created for ESP-IDF. It took just a couple of minor modifications to adapt it to Arduino. Converting the magnitude to amplitude is pretty straightforward with this library (see the .ino file). Both the frequency and amplitude have excellent accuracy. 

The FFT.h file contains the functions defined in Robin Scheibler's library, adapted to Arduino. The FFT_signal.h contains the signal related variables and the actual signal. Just replace the FFT_N with the number of samples, TOTAL_TIME with the time taken to collect the samples, and the fft_signal array with your actual signal, and you are all set!

Edit: Super thanks for @MichielfromNL for taking the efforts to convert this code into a library. You can find the details [here](https://github.com/yash-sanghvi/ESP32/issues/1).
