## Nube (Clouds ported to Max For Live) on Windows build notes

point was to get nube to work on windows, since it came with a mac compiled max external.  via nube related links, i found where it got the code for its clouds external, and i tried to compile that port for windows.  these are the notes from that attempt.

### why?

because i played with VCV rack a bit, and i fell in love with clouds (which in turn made me get a bit into granular synthesis in general, esp as a realtime effect, which seems like the less common usage compared to granular based on static samples).  i couldn't get VCV rack to be as stable as i wanted it to be in my usual ableton and reason workflow, so i didn't keep using it a ton, but i've been chasing clouds-like realtime granular as an effect in my usual setup since then.

shoutout to [Grain Mill](https://maxforlive.com/library/device/4808/grain-mill), which has provided me some very nice realtime granulation in clouds' absence.  also, of course, henke's granulator II, which can make for some nice not-quite-realtime granulation with the input device and an easily accessible control linked to the capture button (like a foot pedal).

## maybe don't bother using this?

i also found https://github.com/xnamahx/NubesMutantes/ -- this seems unrelated to Nube (despite the similar name) and also seems like a more faithful port of the original Clouds code to a Max external.  also, the author of this Max external port and the Max for Live device that uses it seem like the same person, whereas the creator of Nube appears to be a different person than the auther of the Max external port of Clouds that Nube uses.

i need to play with NubesMutantes and Nube, and see which works better and is more stable.  Nube crashed on me once (and brought Ableton down with it) when i did some slightly complex control macro mapping (had a couple macro knobs controlling two nube params each, was manipulating both simultaneously, got a crash).

if NubesMutantes works well, i'd just use that.

have not tried to build NubesMutantes.


## links
* https://maxforlive.com/library/device/6402/nube-texture-synthesizer -- the max for live device with a mac-only max external (port of clouds firmware) that i wanted to use on windows
  * https://bit-01.net/free/
* https://vboehm.net/
* https://vboehm.net/2020/02/mutable-instruments-max-port/
* https://github.com/v7b1/vb.mi-dev -- the code it used for its build of the clouds max external
* https://github.com/pichenettes/eurorack/tree/master/clouds -- the origina Mutable Instruments firmware source code, by Emilie Gillet
* https://github.com/xnamahx/NubesMutantes/ -- a different port of clouds' firmware to a max external and max for live device.  looking at the source and diffing against mutable instruments' firmware, it seems like this max external is a more faithful port than the Volker Böhm port that nube uses.  also, despite the similar project names, NubesMutantes seems unlrelated to Nube.
* https://github.com/VCVRack/AudibleInstruments/blob/v0.6/src/Clouds.cpp

## really rough notes of what i did, taken after the fact

* had to install visual studio 2017 community edition and more of the C/C++/.NET/Windows tooling than i expected, maybe 5 or 6 GB worth
  * that allowed me to build via cmake per the vb.mi-dev instructions
* had to work thought build errors by modifying the source
* was able to get a number of externals to build, including Clouds
  * all were single files
* dropped the file for the clouds external into nube in the same dir that contained the mac external.  i then deleted the mac external.
  * the mac external was a folder, with a different extension than the windows external file.

## remaining build errors

* brds_tilde
* elmnts_tilde
* omi_tilde
* reson_tilde
* rngs_tilde
* rppls_tilde
