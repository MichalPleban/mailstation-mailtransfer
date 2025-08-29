# Mailtransfer

The mailtransfer.exe utility is used to transfer application files to the CIDCO Mailstation via a printer port cable, as well as read dumps of the code and data flash ROM and reflash the device firmware.

You will need:

 * A so-called Laplink cable to connect two printer ports.
 * A physical DB-25 printer port. If your computer is not equipped with one, get a PCI or PCIe card with such a port (an USB port will NOT work).

You need to open Windows Device Manager, find your printer port, double-click it (it will most likely be named LPT1 or LPT3) and note the I/O port address from the "Resources" tab. For example, on my Thinkpad T60 the port address is 03BC while on my Lenovo Desktop with a PCIe card it is F100.

You need to pass the port address in the -p option when running mailtransfer.exe, preceding it with 0x, so for example: -p 0x03bc

The utility uses a Windows DLL to directly access the printer port. On Windows Vista and above, you MUST install the appropriate driver first via the InstallDriver.exe file.

## Credits

Originally developed by Kris Bahnsen: https://github.com/kbembedded/mailstation
