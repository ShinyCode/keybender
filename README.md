![Keybender](/res/keybender_banner.png)
**Keybender** takes your computer and turns it into an easy-to-use, full-fledged performance studio. At the most basic level, Keybender allows you to use any computer keyboard as a MIDI controller, replacing the need for any often-expensive additional hardware. From here, **Keybender** adds three key features:

1. **Live performance.** This feature is most similar to a traditional instrument, and can be accessed by simply pressing keys on your keyboard. With a full range of 51 notes, this is perfect for both solo performance and accompaniment.
2. **Track recording.** This feature allows you to record and save MIDI tracks for later use. The track length, voice, and quantization are all customizable, allowing for great control over the recorded track.
3. **Live song playback.** This feature allows you to assemble a song on the fly by loading and queueing tracks into the 14 available playback channels. Playback can be used in tandem with live performance and recording, giving you the freedom to improvise to your heart's content.

## Table of Contents
- [Setup](#id-setup)
  - [Minimal Setup (High Latency)](#id-setup-min)
  - [Full Setup (Low Latency, Windows only)](#id-setup-full)
  - [Recommended Keyboard Configuration](#id-keyboard-config)
- [Features & Controls](#id-features)
  - [Keyboard Note Layout](#id-keyboard-layout)
  - [Playing Live](#id-playing-live)
  - [Recording a Track](#id-recording)
  - [Binding Tracks to Channels](#id-binding-tracks)
  - [Playing Back Your Tracks](#id-playing-tracks)
  - [Saving and Loading Your Workspace](#id-saving-loading)
- [Gallery](#id-gallery)
- [Licenses & Dependencies](#id-licenses)

## <div id='id-setup'/>Setup
The following sections detail how to set up Keybender on your system, as well as any 3rd-party software needed to boost performance. As of current, **Keybender** has only been tested on Microsoft Windows.

### <div id='id-setup-min'/>Minimal Setup (High Latency)
Running **Keybender** with the minimal setup allows you to explore **Keybender** without installing any third-party software, but comes at the cost of having noticeably high  latency. This can make live performance and recording more difficult.

**To run Keybender using the minimal setup:**

1. On Windows, run the **Keybender** executable (*keybender.exe*).  
![Keybender icon](/res/exe_icon.png)
2. Select a port from the dropdown menu on the right hand side of the application.  
![Selecting a port](/res/min_select_port.png)
3. In order to play notes using the keyboard, don't forget to give focus to the Piano Keyboard Display.

### <div id='id-setup-full'/>Full Setup (Low Latency, Windows only)
Running **Keybender** with the full setup requires more third-party software, but greatly reduces the latency experienced during live performance.

**To install the necessary 3rd-party software:**

1. Make sure to first install the *ASIO4ALL* driver, which can be downloaded here: [Website](http://www.asio4all.com/)
2. Then, install *loopMIDI*, which will enable you to add a virtual MIDI port to your computer: [Website](http://www.tobias-erichsen.de/software/loopmidi.html)
3. Afterwards, install *SyFonOne*, which will enable you to use *ASIO4ALL* with **Keybender**: [Website](http://www.synthfont.com/About_SyFonOne.html)

**Afterwards, Keybender can be started as so:**

1. Start *loopMIDI* if it is not already running. If there is no virtual MIDI port listed, add one using the (+) button at the bottom.  
![Adding a virtual MIDI port in loopMIDI](/res/loopmidi_screen.png)
2. Start *SyFonOne*. Under "Options", select the *loopMIDI* port you created. Under the ASIO settings, check "Use ASIO", and select *ASIO4ALL v2*.  
![Configuring SyFonOne](/res/syfonone_screen.png)
3. In the main window of *SyFonOne*, click "Play". This will activate *ASIO4ALL*. Note that while "Play" is selected, no other applications will have access to the computer's sound card.  
![Activating ASIO4ALL](/res/syfonone_play.png)
4. Run the **Keybender** executable (*keybender.exe*). Select the *loopMIDI* port from the dropdown menu on the right hand side of the application.  
![Selecting a port](/res/full_select_port.png)
5. In order to play notes using the keyboard, don't forget to give focus to the Piano Keyboard Display. The latency should be barely noticeable now.

### <div id='id-keyboard-config'/>Recommended Keyboard Configuration
While only a single keyboard is needed to run **Keybender**, very often, keyboards do not have n-key rollover. This means that they can only register a certain number of simultaneous keypresses. This issue is further compounded by the fact that the USB interface only allows a maximum of 6 non-modifier keys to be pressed simultaneously. In addition, having only a single keyboard can make fingering complex songs incredibly awkward and difficult. The workaround here is to use two keyboards - one for the left hand, and one for the right hand. It is recommended, although not required, that one of the keyboards have a numeric keypad, as these keys serve as a shortcut for changing the instrument's key.

## <div id='id-features'/>Features & Controls

### <div id='id-keyboard-layout'/>Keyboard Note Layout
The key configuration used by **Keybender** is as shown in the following diagram:  
![Keyboard layout](/res/keyboard_layout.png)
Here, notes are expressed in terms of the number of semitones to the datum note (marked in blue), which is set by default to middle C (note #60). Thus, **Keybender** can play notes ranging from datum -24 to datum +26. Sustain is accomplished by using the spacebar, similar to how a piano's sustain pedal is operated. While the numeric keypad is a handy shortcut for changing the key of the instrument, the datum note can still be set manually using the "Edit" menu up top.

### <div id='id-playing-live'/>Playing Live

**To play notes:**  
Make sure that the piano keyboard display currently has focus. If not, simply click within its boundaries. Afterwards, you should be able to play notes by pressing the keys on your keyboard according to the layout prescribed above.

**To turn on the click:**  
Set the tempo for the click via the button in the player controls. Then, select the desired number of pickup beats with pickup slider. Toggle the click button to "on", and then click the play button. You click should now be active.

**To turn off the click:**  
Toggle the click button to "off", which will prevent the click from sounding on the next beat. To stop all playback, click the stop button.

### <div id='id-recording'/>Recording a Track
**Recording a track:**  
Set the tempo for the track to be recorded at. Note that this does not have to be the final tempo, as playback of all tracks scales according to the currently selected tempo. Then, select the amount of quantization from the quantization menu. "Q128", for example, means that the `EVT_KEY_DOWN` and `EVT_KEY_UP` events will be rounded to the nearest 1/128 beat, while "Q2" means that they will be rounded to the nearest 1/2 beat. Afterwards, select the desired number of pickup beats, and change the instrument voice if desired. In the track menu, select the track to record to (0-63). Finally, when you are ready to begin recording, press the record button which corresponds to the length of the track in beats. Recording will automatically start after the appropriate number of pickup beats have been played.

### <div id='id-binding-tracks'/>Binding Tracks to Channels
By themselves, your recorded tracks will not automatically play - they are only patterns stored in memory. In order for them to play, you must bind the track to a specific channel.

**Binding a track to a channel:**  
Select the desired track in the track selector, and then click "Load" in the desired channel. Note that channel 9 in Keybender is reserved, by convention, for percussion. You should see the bound track number appear to the right of the channel's name.

**Clearing a channel:**  
To clear the bound track from a channel, simply press the clear button. The track number slot to the right of the channel's name should now be empty.

**Overriding the instrument of a track:**  
By default, a track will play using the same instrument it was recorded with. To override this, press the "I" button, and enter the desired instrument to use. To reset the instrument to the default specified by the track, simply enter "-1".

### <div id='id-playing-tracks'/>Playing Back Your Tracks
Keybender is designed to allow you to mix and match tracks while playback is occurring. To this end, there exist not only playback controls for the entire song, but also playback controls for each individual channel. So, creating a live mashup is a matter of binding and playing multiple tracks while the "Play" button is down.

**Playing back your tracks:**  
To begin playback, set the desired tempo and pickup, and press "Play". The step counter in the information panel will start incrementing. Any tracks that were already loaded into channels will begin looping after the appropriate number of pickup beats has passed. In order to ensure that tracks do not overlap, most actions you take will be queued, and not take place until the next time the track is due to repeat.

**To bind a track to a channel during playback:**  
Follow the instructions in the previous section to bind the track to the channel. The operation remains exactly the same.

**To clear a channel during playback:**  
Follow the instructions in the previous section to clear the channel. The operation remains exactly the same.

**To queue a channel to play:**  
Press the "P" button in the associated channel. The indicator square to the right of the channel will turn green, and the channel will start playing when the track is next due to repeat.

**To queue a channel to stop playing:**  
Press the "S" button in the associated channel. This will stop the track after it finishes playing through once.

**To force a channel to stop playing:**  
Press the "SN" button in the associated channel. This will stop the track instantly, without waiting for it to finish playing.

### <div id='id-saving-loading'/>Saving and Loading Your Workspace
In **Keybender**, your collection of recorded tracks, channel settings, and playback settings comprise your workspace. This can be saved to a file and loaded so you can resume your work at a later time. Note that saving and loading uses *cPickle*, so only load workspaces from trusted sources.

**To save your current workspace**  
Up top, click "File", and then "Save workspace". The first time you save a workspace, you will be prompted to give it a name and specify its save location.

**To save your current workspace under a different name**  
Up top, click "File", and then "Save workspace as...". You will be prompted to give the workspace a new name and specify its save location.

**To load a workspace**  
Up top, click "File", and then "Load workspace...". You will be prompted to choose the workspace to load into **Keybender**.

## <div id='id-gallery'/>Gallery

## <div id='id-licenses'/>Licenses & Dependencies
 * **Keybender** is licensed under the MIT license.  
 * *wxPython* is used as a GUI toolkit and *Mido* is used for sending MIDI messages and working with ports. These do not need to be installed by the user.  
 * *ASIO4ALL*, *loopMIDI*, and *SyFonOne* are used to achieve low latency. These are not included and must be installed by the user.
