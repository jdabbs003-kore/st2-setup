# st2-setup
## Simtrace2 Environment Setup
This project sets up a Simtrace2/Wireshark environment to log live traffic between a cellular modem and its SIM card.

### Hardware
There are two basic setup options:
1. Simtrace2 and Wireshark both installed on a Debian computer, and
1. Simtrace2 installed on a Debian computer, and Wireshark installed on a Windows computer.

### Setup Option 1
You'll need a Debian 11 computer and a Simtrace2 board (available [here](https://shop.sysmocom.de/SIMtrace2-Hardware-Kit/simtrace2-kit)).
#### Setup
From the bash shell in the Debian computer, perform the following steps.
1. `wget -O ./setup https://github.com/jdabbs003-kore/st2-setup/blob/main/setup?raw=true`
1. `chmod 777 setup`
1. `sudo ./setup`
1. `sudo apt-get wireshark`

#### Operation
1. Setup the hardware -- the DUT, the Simtrace2 board, and the SIM, and plug
the Simtrace2 USB port into the Debian computer. Leave the DUT powered
off.
1. Launch wireshark from the Debian UI, and set up the following display
filter: (udp.dstport==4729)
1. Launch the Simtrace2 sniffer as follows from the bash shell, as follows:
`simtrace2-sniff`

1. Power on and setup the DUT.

simtrace2-sniff will echo a log to the screen and also send packets to wireshark.
### Setup Option 2
You'll need a Debian 11 computer, a Windows computer, and a Simtrace2 board (available [here](https://shop.sysmocom.de/SIMtrace2-Hardware-Kit/simtrace2-kit)).
#### Debian Setup
From the bash shell in the Debian computer, perform the following steps.
1. `wget -O ./setup https://github.com/jdabbs003-kore/st2-setup/blob/main/setup?raw=true`
1. `chmod 777 setup`
1. `sudo ./setup`

#### Windows Setup
Install wireshark from [here](https://www.wireshark.org/).
#### Operation
1. Setup the hardware -- the DUT, the Simtrace2 board, and the SIM, and plug
the Simtrace2 USB port into the Debian computer. Leave the DUT powered
off.
1. Launch wireshark on the windows computer, and set up the following display
filter: (udp.dstport==4729)
1. Launch the Simtrace2 sniffer as follows from the bash shell, as follows:
`simtrace2-sniff -i <windows ip address>`

1. Power on and setup the DUT.

simtrace2-sniff will echo a log to terminal screen and also send packets to wireshark on the Windows computer.
