Working with Captures / The MN10
================================

One of the more helpful filters is frame.len > 64, but note that the MN10 seems to operate a state machine and needs reads from the endpoint to *work*. It's not a very asynchronous device.

It's also not a very good USB device, the M-Crew software largely drives the bulk endpoints and doesn't do anything with control interfacves.

Since I'm ultimately on a Linux host, the captures are Linux URBs detailed here: https://docs.kernel.org/driver-api/usb/URB.html
