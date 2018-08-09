# Light-Transmitted-Video
Research towards sending video using visible light 

Includes files from 

Files:

audio_RXTX.grc
  Includes both a transmitter and receiver flow for sending audio between two usrp's connected to the same machine.
  To use, replace the file in the "Wav File Source" block with any .wav file, and then create another .wav file for the "Wav. File Sink".     side. 

audio_RXTX_transmit.grc
  The transmitter flow from audio_RXTX.grc only. For sending an audio file to another machine with a usrp.

audio_RXTX_receiver.grc
  The reciever flow from audio_RXTX.grc only. For receiving an audio file from another machine with a usrp.

video_RXTX_sim.grc
  Simulation of a video transmission. Does not currently work completely. 
  It simulate sending a MPEG transport stream (.ts) file using the "File Source" and "File Sink" block, but requires a video player, such as VLC Media Player, to be simultaneiously playing the "received" file. This is not reliable, as the video "received" is either slanted, choppy, or nonexistent. 
  The UDP blocks can be used to receive and send streams of video from applications such as VLC Media Player or Gstreamer. The IP address field needs to be filled with the machine's IP address, and the port must match the media player's port. The port for the "UDP Source" must be different from the port for the "UDP Sink". 
  
video_RXTX.grc
  Same as "video_RXTX_sim.grc", just with usrp's instead of a direct connection between the transmitter and receiver portions.
