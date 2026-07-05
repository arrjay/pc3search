Capturing USB Traffic in Windows XP
===================================

- Install USBPcap 1.5.3.0 (the last XP supporting release) from https://github.com/desowin/usbpcap/releases/tag/1.5.3.0

- After installation, open a command prompt, navigate to the USBPcap install directory (`C:\Program Files\USBPcap`) and run `USBPCapCMD.exe` - this will pop up it's own command box (but weirdly I had issues just double-clicking it in Explorer...) and provide you with a list of capture filter devices. One of the capture filters should mention a child device named `SONY LINK KIT` or `SONY USB COMM` - type the number of the filter you wish to monitor. Next, provide an output file name - I used `output.pcap` but this is your choice. Once USBPcapCMD is running, start M-Crew, potentially taking notes on what you did during the M-Crew session. I would avoid actually recording any audio if your audio device is on the same USB filter - this will result in a LARGE capture file. Once you are done with M-Crew, press Ctrl-C to exit USBPcapCMD. The file can now be copied out and opened in WireShark.

![screenshot of Windows XP system running USBPcap](/xp-usbpcap.png)
