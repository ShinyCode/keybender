# keybender
blurb goes here

## Table of Contents
- [Setup](#id-setup)
  - [Minimal Setup (High Latency)](#id-setup-min)
  - [Full Setup (Low Latency, Windows only)](#id-setup-full)
  - [Recommended Keyboard Configuration](#id-keyboard-config)
- [Features](#id-features)
  - [Keyboard Note Layout](#id-keyboard-layout)
  - [Playing Live](#id-playing-live)
  - [Recording a Track](#id-recording)
  - [Creating a Song/Mashup](#id-creating-song)
- [Gallery](#id-gallery)
- [Licenses & Dependencies](#id-licenses)

## Setup<div id='id-setup'/>
The following sections detail how to set up Keybender on your system, as well as any 3rd-party software needed to boost performance. As of current, Keybender has only been tested on Microsoft Windows.

### Minimal Setup (High Latency)<div id='id-setup-min'/>
Running Keybender with the minimal setup allows you to explore Keybender without installing any third-party software, but comes at the cost of having noticeably high  latency. This can make live performance and recording more difficult.

**To run Keybender using the minimal setup:**

1. On Windows, run the Keybender executable (keybender.exe).
2. Select a port from the dropdown menu on the right hand side of the application.
3. In order to play notes using the keyboard, don't forget to give focus to the Piano Keyboard Display.

### Full Setup (Low Latency, Windows only)<div id='id-setup-full'/>
Running Keybender with the full setup requires more third-party software, but greatly reduces the latency experienced during live performance.

**To install the necessary 3rd-party software:**

1. Make sure to first install the ASIO4ALL driver, which can be downloaded here: [LINK]
2. Then, install loopMIDI, which will enable you to add a virtual MIDI port to your computer: [LINK]
3. Afterwards, install SyFonOne, which will enable you to use ASIO4ALL with Keybender: [LINK]

**Afterwards, Keybender can be started as so:**

4. Start loopMIDI if it is not already running. If there is no virtual MIDI port listed, add one using the (+) button at the bottom. [IMG]
5. Start SyFonOne. Under "Options", select the loopMIDI port you created. Under the ASIO settings, check "Use ASIO", and select ASIO4ALL v2.
6. In the main window of SyFonOne, click "Play". This will activate ASIO4ALL. Note that while "Play" is selected, no other applications will have access
   to the computer's sound card.
7. Run the Keybender executable (keybender.exe). Select the loopMIDI port from the dropdown menu on the right hand side of the application.
8. In order to play notes using the keyboard, don't forget to give focus to the Piano Keyboard Display. The latency should be barely noticeable now.

### Recommended Keyboard Configuration<div id='id-keyboard-config'/>
While only a single keyboard is needed to run Keybender, very often, most keyboards are not n-key rollover. This means that they can only register a certain number of simultaneous keypresses. This issue is further compounded by the fact that the USB interface only allows a maximum of 6 non-modifier keys to be pressed simultaneously. In addition, having only a single keyboard can make fingering complex songs incredibly awkward and difficult. The workaround here is to use two keyboards - one for the left hand, and one for the right hand. It is recommended, although not required, that one of the keyboards have a numeric keypad, as these keys serve as a shortcut for changing the instrument's key.

## Features<div id='id-features'/>

### Keyboard Note Layout<div id='id-keyboard-layout'/>

### Playing Live<div id='id-playing-live'/>

### Recording a Track<div id='id-recording'/>

### Creating a Song/Mashup<div id='id-creating-song'/>

## Gallery<div id='id-gallery'/>

## Licenses & Dependencies<div id='id-licenses'/>
