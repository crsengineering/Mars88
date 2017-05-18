Ringserver
https://seiscode.iris.washington.edu/projects/ringserver/wiki


"Ringserver is a generic ring buffer"


We can create SeedLink server just using ringserver.
In short there are two ways:
- create 512-byte miniSEED data records to be feed to ringserver (as done in this application)
- feed ringserver through TCP/IP (such when using data from EarthWorm ring buffer)

In this application we will create 512-byte miniSEED files from raw data (from Mars88).
