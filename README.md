# Table of Contents

[Overview](#Overview)<br/>
[Download](#Download)<br/>
[Install Notes](#InstallNotes)<br/>
[Documentation, Support, and Contact](#DocumentationSupport)<br/>

<a name="Overview"></a>
# Overview

This page links to Hypersignal-Macro software download and documentation, and contains some updated install and run-time notes.

Hypersignal-Macro was popular signal processing software in the 1990s, and can still be useful in some situations, including:

* fast/quick time domain and frequency domain analysis, including sliding FFT, convolution, and 2-D and 3-D spectrographic display
* import and display of arbitrary time domain waveform file formats, for example files with no headers, in hex ASCII formats, with odd number of nibbles per sample (e.g. 12 bits per sample), with swapped bytes, with mean or bias that should be subtracted, etc.
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

    -set the DRIVE field to C:
    -set the SUBDIRECTORY field to \waveform\

<b>3</b> &nbsp; For best graphics results, the DOSBox config file should have this setting:

    machine=svga_et4000

and Hypersignal the graphics config option should be set to 94 (Tseng Labs 4000 video card, 1024x768 256 color). Probably Tseng Labs 3000 would work also (800x600 256 color).

The default DOSBox config setting is "svga_s3", which is an S3 Trio64 card, considered to implement the VESA Std 800x600 mode in a widely compatible way.  This corresponds to graphics config selection 95, which also works fine with the svga_et4000 machine setting, but doesn't support the new grayscale and heatmap 2-D Spectrograph options (see below).

<b>4</b> &nbsp; To speed up Hypersignal operation, press ctrl-F12 repeatedly ... something around "30000 cycles" (shown after "Cpu Speed" in the DOSBox main menu bar) seems to work fairly well.  A default CPU speed can also be set in the DOSBox config file.

<b>5</b> &nbsp; After using the mouse inside Hypersignal (either menu or graphical displays), press ctrl-F10 to return mouse control to the desktop.  For example to take a screen cap of a Hypersignal display, adjust the display as needed with the mouse, including zoom and markers, then press ctrl-F10, then press Alt-PrntScrn, then use MS Paint or other program to paste from the clipboard.

<b>6</b> &nbsp; Waveform file notes:

* .tim and .wav file formats are supported in all time domain functions
* the tim2wav and wav2tim macro functions can be used to convert
* filenames are limited to 8 characters; the old DOS format of appending '~N' applies for longer filenames

<b>7</b> &nbsp; In the 2-D Spectrograph display function, to use 16-level grayscale, enter:

    G2,16

in the CONTOUR field.  To use 19-level color, enter:

    C3,19
  
in the CONTOUR field.  Note that the second value is number of discrete gray or color levels.  Other levels can be entered also (up to 257) but currently won't improve contour resolution.  If someone wants to program Hypersignal source code to make use of custom DOS 256-bit color palettes in order to obtain better contour resolution, please contact Signalogic.

<a name="DocumentationSupport"></a>
# Documentation, Support, and Contact

Original Hypersignal documentation is located here:

  ftp://ftp.signalogic.com/documentation/Hypersignal/

For issues or questions about the download, please click on Issues above and post your questions.  If needed, you can send e-mail to Signalogic at info at signalogic dot com.
