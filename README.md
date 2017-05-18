# Mars88
Upgrade Mars88 to SeedLink

Mars88 from Lennartz Electronics is an obsolete instrument if compared to other digitizers such Q330, Titan SMA and many others, but still working in some seismic networks.

Defects of Mars88:
- original timing system based on DCF timing signal
- serial communication using radio-modem
- data transmission not in real-time mode

About timing we can use GPS to DCF converter (board we have been using for several years has made by Sara electronics from Perugia - ITALY), in this way DCF signal is more stable and sync is more quick (5-6 minutes after GPS locks satellites).

Radio-modem usually works with analog transceivers @433MHz, nowdays we use digital radios running @2,4/5GHz; in this case we need serial-to-ethernet converter such Moxa N-Port devices; some radio (such Routerboard RB433) is provided of serial port, so you don't need external devices.
At this point we are connected to Mars88, but still working with Lennartz software.

SeedLink is a standard protocol for data exchange, so why not use this?
Ok, first we need a plugin (1) to read raw data from Mars88 using serial interface (the only one available on Mars88).
Then we need a way to encode raw data into SeedLink: in this case we could use a Ringserver (2) or write a plugin for EarthWorm (more complex).

Now there are two options:
- plugin running on central server, collecting data from all Mars88 through TCP/IP (in this case we need a serial to ethernet converter for every Mars88), feeding Ringserver
- plugin running locally (one for every Mars88) on remote linux device (PC, Raspberry Pi, or similar), connected to Mars88 through serial port (or if you want you can use TCP/IP with serial to ethernet converter, but in this case using simple serial connection is more easy). 

I'm planning to start using Raspberry Pi (cheaper and low power) as local server, to be connected to Mars88 through serial port.
If this would correctly work I'm going to design board based on different SBC than Raspberry Pi, to be mounted internally Mars88.

(1) Paolo Di Bartolomeo - OGS Trieste - ITALY

(2) IRIS-EDU

