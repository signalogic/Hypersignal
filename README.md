# Table of Contents

[Overview](#Overview)<br/>
[Download](#Download)<br/>
[Install Notes](#InstallNotes)<br/>
[Sample Displays](#SampleDisplays)<br/>
[Documentation, Support, and Contact](#DocumentationSupport)<br/>

<a name="Overview"></a>
# Overview

This page links to Hypersignal-Macro software download and documentation, and contains some updated install and run-time notes.

Hypersignal-Macro was popular signal processing software in the 1990s and early 2000s, and can still be useful in some situations, including:

* fast/quick time domain and frequency domain analysis, including sliding FFT, convolution, and 2-D and 3-D spectrographic display
* import and display of arbitrary time domain waveform file formats, for example files with no headers, in hex or decimal/fp ASCII formats, with odd number of nibbles per sample (e.g. 12 bits per sample), with swapped bytes, with mean or bias that should be subtracted, etc.
* IIR and FIR filter design and application
* difference equations
* testing old / legacy DSP and data acquisition cards

<a name="Download"></a>
# Download

The hsmacro.zip file should be downloaded to a Win folder and unzipped (suggest to use c:\hsmacro).  A "waveform" subfolder should be created.  The .zip file is not self-executing.

<a name="InstallNotes"></a>
# Install Notes

For WinXP and up, Hypersignal must be run inside DOSBox (v0.74 or higher).  Here are the basic steps.

<b>1</b> &nbsp; Run DOSBox and execute the following commands:

    mount c c:\hsmacro
    c:
    hsm

Hypersignal should run and the menu interface should appear (a default hsmacro.cnf file is included in the zip file so you should not see prompts for mouse and graphics drivers).

<b>2</b> &nbsp; Inside Hypersignal, in the User Setup menu:

    set the DRIVE field to C:
    set the SUBDIRECTORY field to \waveform\

<b>3</b> &nbsp; For best graphics results, the DOSBox config file should have this setting:

    machine=svga_et4000

and the Hypersignal graphics config option should be set to 94 (Tseng Labs 4000 video card, 1024x768 256 color). Probably Tseng Labs 3000 would work also (800x600 256 color).  If you're not using the DOSBox config file, or otherwise want to stay lean and mean (in the true spirit of Hypersignal :-), you can right-click the DOSBox desktop icon, select Properties and then the Shortcut tab, and add the following to the "Target" entry:

    -machine svga_et4000

After doing that, the Target entry might look something like:

    "C:\Program Files (x86)\DOSBox-0.74\DOSBox.exe" -userconf -machine svga_et4000

Then click on Apply to save.  The Target entry is effectively the DOSBox cmd line that will be executed when you double-click on the DOSBox icon.  Keep in mind the above cmd line is just an example only and the correct cmd line for your Win system is likely to be different.

After changing the DOSBox config file or Properties cmd line, DOSBox has to be restarted for changes to take effect.  If you're already inside Hypersignal you can exit and restart from Step 1 above.

The default DOSBox config setting is "svga_s3", which is an S3 Trio64 card, considered to implement the VESA Std 800x600 mode in a widely compatible way.  This corresponds to graphics config selection 95, which also works fine with the svga_et4000 machine setting, but doesn't support the new grayscale and heatmap 2-D Spectrograph options (see below).

<b>4</b> &nbsp; To speed up Hypersignal operation, press Ctrl-F12 repeatedly ... something around "30000 cycles" (shown after "Cpu Speed" in the DOSBox main menu bar) seems to work fairly well.  A default CPU speed can also be set in the DOSBox config file.

<b>5</b> &nbsp; After using the mouse inside Hypersignal (for either menu or graphical displays), press Ctrl-F10 to return mouse control to the desktop.  For example to take a screen cap of a Hypersignal display, adjust the display as needed with the mouse, including zoom and markers, then press Ctrl-F10, then press Alt-PrntScrn to copy to the Win clipboard, then use MS Paint or other program to paste from the Win clipboard.

<b>6</b> &nbsp; Waveform file notes:

* .tim and .wav file formats are supported in all time domain functions
* the tim2wav and wav2tim macro functions can be used for format conversion
* filenames are limited to 8 characters; for longer filenames the old DOS convention appending '~N' applies

<b>7</b> &nbsp; In the 2-D Spectrograph display function, to use 16-level grayscale, enter:

    G2,16

in the CONTOUR field.  To use 19-level color "heatmap", enter:

    C3,19
  
in the CONTOUR field.  Note that the second value is number of discrete gray or color levels.  Other levels can be entered also (up to 257) but currently won't improve contour resolution.  The C3 heatmap option is modeled after newer R and Matlab "perceptual color domain" options (e.g. "inferno colors").

If someone wants to program Hypersignal source code to make use of custom DOS 256-bit color palettes in order to obtain better contour resolution, please contact Signalogic.

<a name="SampleDisplays"></a>
# Sample Displays

Below are a few sample displays captured on a Win10 system, including frequency domain 2-D and 3-D, IIR filter design, and a simple difference equation.
<br/>
&nbsp;
<br/>

![Image](https://github.com/signalogic/Hypersignal/blob/master/images/dtmf_tones_2d_spectrograph.png?raw=true "DTMF tones, 2-D Spectrograph display")

![Image](https://github.com/signalogic/Hypersignal/blob/master/images/speech_2d_spectrograph.png?raw=true "Before and after AMR-WB encoded speech, 2-D Spectrograph display")

![Image](https://github.com/signalogic/Hypersignal/blob/master/images/speech_3d_spectrograph.png?raw=true "Before and after AMR-WB encoded speech, 3-D Spectrogram display")

![Image](https://github.com/signalogic/Hypersignal/blob/master/images/wavelet_2d_spectrograph.png?raw=true "Wavelet display in 2-D Spectrograph format")

![Image](https://github.com/signalogic/Hypersignal/blob/master/images/iir_filter_design.png?raw=true "IIR elliptic filter design")

![Image](https://github.com/signalogic/Hypersignal/blob/master/images/hanning_window_difference_equation.png?raw=true "Hanning window difference equation")

<a name="DocumentationSupport"></a>
# Documentation, Support, and Contact

Complete Hypersignal documentation is located here:

&nbsp;&nbsp;&nbsp;ftp://ftp.signalogic.com/documentation/Hypersignal/

Legacy web pages are located here:

&nbsp;&nbsp;&nbsp;https://www.signalogic.com/hypersignal_macro

&nbsp;&nbsp;&nbsp;https://www.signalogic.com/hypersignal_acoustic

For problems or questions about the download such as missing files, please click on Issues above and post an issue description.  If needed, you can send e-mail to info at signalogic dot com.
