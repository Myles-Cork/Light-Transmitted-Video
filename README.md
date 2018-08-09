# Light-Transmitted-Video
Research towards sending video using visible light

Reqirements:
Gnuradio, UHD, VLC Media Player, Gstreamer


Files:

audio_RXTX.grc:

  Includes both a transmitter and receiver flow for sending audio between two usrp's connected to the same machine.
  To use, replace the file in the "Wav File Source" block with any .wav file, and then create another .wav file for the "Wav. File Sink".

audio_RXTX_transmit.grc:
  The transmitter flow from audio_RXTX.grc only. For sending an audio file to another machine with a usrp.

audio_RXTX_receiver.grc:
  The reciever flow from audio_RXTX.grc only. For receiving an audio file from another machine with a usrp.

video_RXTX_sim.grc:
  Simulation of a video transmission. Does not currently work completely. 
  It simulate sending a MPEG transport stream (.ts) file using the "File Source" and "File Sink" block, but requires a video player, such as VLC Media Player, to be simultaneiously playing the "received" file. This is not reliable, as the video "received" is either slanted, choppy, or nonexistent. 
  The UDP blocks can be used to receive and send streams of video from applications such as VLC Media Player or Gstreamer. The IP address field needs to be filled with the machine's IP address, and the port must match the media player's port. The port for the "UDP Source" must be different from the port for the "UDP Sink". 
  A stream can be started using VLC Media Player by going to media, Stream, adding the file to be streamed, then clicking on the "Stream" button. After clicking "Next", select from the dropdown UDP, and then Add. Type the IP address of the machine, and the port you want to transmit on (for the simulations the default is 5003), then click "Next". Then select the profile (MP4), then click "Next", and finally "Stream". 
  To open a stream, got to media, "Open Network Stream", and then type in udp://@:portname or udp://@ipaddress:portname , replacing portname and ipaddress with the port for the receiver's udp sink and the machines ip address respectively. 
  
video_RXTX.grc:
  Same as "video_RXTX_sim.grc", just with usrp's instead of a direct connection between the transmitter and receiver.
