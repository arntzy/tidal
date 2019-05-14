[ SuperCollider MidiOut For Linux: ](http://doc.sccode.org/Classes/MIDIOut.html#Linux%20specific:%20Connecting%20and%20disconnecting%20ports )

[Tidal Midi connection to Supercollider](https://tidalcycles.org/index.php/SuperDirt_MIDI_Tutorial)

Before starting SuperCollider: You must configure the jackd server to be at 44100 with 256 period:

jackd -d alsa --device hw:0 --rate 44100 --period 256 -n2

# To load new samples into SuperDirt:
~dirt.loadSoundFiles("full/path/to/directory/*")

# to use jack to play audio through the system audio:
export JACK_PLAY_CONNECT_TO=system:playback_%d

<!--  To test the wav: -->
jack-play test.wav

<!-- To Record: -->
Server.default.record;

<!-- To Stop Recording: -->
Server.default.stopRecording

<!-- Convert a directory of samples from mp3 to wav -->
for f in ls *.mp3; do ffmpeg -i $f $(basename $f).wav; done

<!-- List the contents of a directory with line numbers -->
ls | cat -n
