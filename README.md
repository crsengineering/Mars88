# Mars88
Upgrade Mars88 to SeedLink

Mars88 from Lennartz Electronics is an obsolete instrument if compared to other digitizers such Q330, Titan SMA and many others, but still working in some seismic networks.

Defects of Mars88:
- original timing system based on DCF timing signal
- serial communication using radio-modem
- data transmission not in real-time mode

About timing we can use GPS to DCF converter (board we have been using for several years has made by Sara electronics from Perugia - ITALY), in this way DCF signal is more stable and sync is more quick (5-6 minutes after GPS locks satellites).

Radio-modem usually works with analog transceivers @433MHz, nowdays we use digital radios running @2,4/5GHz; in this case we need serial-to-ethernet converter such Moxa N-Port devices.
At this point we are connected to Mars88, but still working with Lennartz software.

SeedLink is a standard protocol for data exchange, so why not use this?
Ok, first we need a plugin to read data from Mars88 using serial port (1).
Then we need a way to encode raw data into SeedLink: in this case we could use a Ringserver (2) or write a plugin for EarthWorm (more complex).




(1) Paolo Di Bartolomeo - OGS Trieste - ITALY
(2) IRIS-EDU
