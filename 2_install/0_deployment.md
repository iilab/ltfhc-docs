
# TODO

# Feedback
 
_From Kalemie_

  - Need message box with Centre de Santé (but Radio should do for now)

_From Kimena_
  - Problem with date in patient DOB form
  - Immunization lists

PCV13 1
PCV13 2
PCV13 3
Vitamin A (100 000 Unite Internationale)
Vitamin A (200 000 UI)

VAR (Anti Rougeole)
VAA (Vaccin Anti Amarile - Fievre Jaune)

*Measles/PENTA*?

# Kigoma

[x] Update Kigoma server
[x] Test provisioned laptop with several servers
[x] Setup Laptops

# Kalemie

## Make sure to

 - Fix the sequence in diff.py
 - Add "clinic" and "clinician" by default.
 - Test EMR when waking up logged out in the couchapp (to avoid having to restart the laptop)
 - Fix the problem with double dates being displayed for DOB

# LOG

## In Kalemie
   - Had to modify the ltfhc-couch docker image by hand. Edit the start script to remove the stud launch and commit.

```
docker ps
[get container id such as cc913c68bce5]
vi /var/lib/docker/aufs/mnt/cc913c68bce5 [autocomplete] /opt/start
[comment all but ./opt/start_couch and save]
docker commit couch iilab/ltfhc-couch
systemctl restart ltfhc-couch.service
```

Check that couch is running without errors
```
docker logs -f couch
```

 - Had to install the ethernet and wifi interfaces in a bridge (to allow access to 192.168.42.1 from the locally create Wifi AP and the Nanostation transparenet bridge) 
   - Usual instructions online don't work for this as they generally (with a few exception) forget to mention that after starting hostapd then the following should be ran (In Kalemie I've installed this in rc.local)

```
ifconfig wlan0 192.168.42.1
brctl addif br0 wlan0
```


## In Kimena

 - Upgrading Namansi box to install in Katondo (replacing defective box)
   - Run kanso from /home/ltfhc-deploy/bin (need to add that in path for node to be found)
   - Installed vhost in local.ini
   - install mgetty conf
   - Ran ansible for radio mgetty config, status and sync scripts.
   - Rerun NGT programming (missing voice only addresses)

## In Katondo

   - The Namansi box (0.4.0) here is not set to restart when plugged in.
   - Success! Was able to log into the ex Wimbi box (which was the one taken on the Katondo trip) - Had to install a DHCP server on the laptop.
   - Now Upgrading the Katondo (ex Wimbi) box.
     - Changed name.
     - Copied ltfhc-next.deploy.20141007.tgz. (to help avoid transfer and make customisation ansible script run properly without git clone)

   - Hiding the channels needs to be done, in admin mode, after hiding the data network, then from the listmanager (long press x), each data channel needs to be hidden (long press glass, config, hide).

TODO: Install nodejs-legacy from .deb. Install npm manually. Install Kanso from npm-registry.

## In Kimena

 - Worked on translation. (about 200 strings)
 - Did channel testing
 - Got data transfer
 - Worry about cron jobs.
 - Time is 14:58 on the box. 7:52 on my laptop.
 - Try to implement uucp Poll. (self-described as simple retry solution)

```
schedule        kalemie 21
poll    kalemie 21 22 23 00 01 02 03 04 05
```

## In Katombo
 - Trying to prepare for diffs by tarballing lthfc-next after each deploy. Should also checksum.
 - Working on translations
 - Working on scheduling (using Poll and cron.d). 
 - Thinking that time should be passed through with uucp down from cloud to kalemie and out.

# Back in Kalemie
 + Checking on voice self-address
 - Doing channel tests
 - Power fluctuation rebooted Radio and server.
 - Found Katondo replies to channel test on data channel 11. Trying ```uucico -S katondo```. Not working
 - Created ansible script to set timezone and time from laptop
 - 

 + Install OpenVPN
 + Reconfigure mgetty (ttyUSB0)
 + Rerun uucp config generation scripts (debug inventory had wrong radio addresses)
 + Create /var/log/ltfhc
 - Check voice self-address

# Back in Kigoma

 - Finalised configuration Kigoma box (update with latest EMR, connected to ltfhc-prod openvpn)
 - Working on Kasovu box
 
```

```

# Notes

## Wifi Link

 - @all (install) Identify mouting points / access point location / server location
 - @tech (install) Mount Wifi Links
 - @tech (configure) [Configure Wifi Links]()
 - @tech (configure) Configure Wifi AP
 - @tech (test) Laptop pings server

## Server

 - @all (install) Location for box
 - 

## 3G connection

## Radio

 - Use ltfhc-radio VM
 - Provision Radios.

## Laptops

## Other Servers if time.

 - Offline update of servers...


# High Level TODOs

Low hanging fruits
 - Make diagnostic list (94 entries) more usable - grouping (Use Ordinogramme)
 - Verify translations with DRC MOH representative

