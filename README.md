Auto shutdown script
========================================================================

Proposal
------------------------------------------------------------------------
Shutdown ZTE device once charger disconnected for period of time.

Tested on devices
------------------------------------------------------------------------
- ZTE MF90+

Install
------------------------------------------------------------------------
1. Download [last version.](https://github.com/dev-x3m/zte-shutdown/archive/master.zip)
2. Unzip and copy ___"scripts/usr"___ to ___"/usr"___ on your device using ftp, ssh or adb
3. Make scripts executable
    ```sh
    $ cd /usr/modules/x3m.asdn
    $ chmod a+x asdn asdnd
    ```
4. Create symlink for init
    ```sh
    $ ln -s /usr/modules/x3m.asdn/asdn /etc/init.d/asdn
    $ ln -s /etc/init.d/asdn /etc/rc5.d/S51asdn
    ```
    
Setup
------------------------------------------------------------------------
`DAEMON`
daemon execution path

`SLEEP`
timeout to next power status check

`WAIT`
timeout to power off after power loss

 Commands
------------------------------------------------------------------------
`asdn start`
start daemon

`asdn stop`
stop and wait daemon for exit

`asdn status`
stop and wait daemon for exit

`asdn restart`
daemon soft restart

`asdn reload`
daemon hard restart

`asdn mode`
display current mode

`asdn auto`
swith to auto mode

`asdn manual`
switch to manual mode

Roadmap
------------------------------------------------------------------------
- add windows/linux installer and uninstaller scripts for ftp, ssh and adb
- split monitoring sleep timeouts (more responsive)
- implement mode switch on power key press
- add monitoring mode to status print
- watchdog (auto restart daemon)
- fix download mode
- update-rc
