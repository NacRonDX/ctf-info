---
tags:
  - steganography
---

Audacity is a GUI based tool. It is an open-source audio editor and recording application software.

### Installation
Audacity is available for Windows, macOS & Linux. You can download [Audacity](https://www.audacityteam.org/download/) from its official site, or in Ubuntu, you can download it from the Ubuntu store.

### Usage
Audacity can be used from the command line or by directly clicking the icon in applications.
	`audacity <file_name>`

Audacity displays the audio files in a wave form. You change the waveform into spectrogram by changing the layer into spectrogram. You can do it by clicking the arrow next to the track name to switch from waveform to spectrogram.

![[audacity_spectogram.png]]
**Spectrogram** is a visual based view of representing the signal strength, or “loudness”, of a signal over time at various frequencies present in a particular waveform.

There are so many effects like changing speed, pitch, tempo etc. By clicking the effects option in the menu bar, you can see many options, and users can apply the effect only in the selected area or the entire track.

### Example
In CTFs we come across quite a few audio challenges. Mostly, these challenges are mainly about changing the layer to spectrogram or they embedding some data in **morse format**.

**Morse Code** means converting the text into **Dot-Dash** format. You can use this [link](https://morsecode.scphillips.com/translator.html) for decoding that morse code. If you hear the audio has **beeps**, it is confirmed that, the audio file contains a morsecode you can directly upload that in this [link](https://morsecode.world/international/decoder/audio-decoder-adaptive.html) and get the message you wanted. In CTFs we get challenges which have the morse code or we see that morse code after changing the layer to spectrogram.

An example for changing the layer to spectrogram
![[audacity_spectogram_flag.png]]

An example for changing the layer and getting the morse code
![[audacity_spectogram_morse.png]]
You can see some extra data above the separation of two tracks, that is nothing but morse. **Big lines** represent **Dash** and **Small lines** represent **Dot**, the space between them separates each letter. If you want a clear idea of each and every letter you can separate it with **/ or |**.

The **morse code** for alphabets and number is as follows
![[audacity_morse.png]]