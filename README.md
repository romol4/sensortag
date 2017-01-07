# sensortag
Sensortag mode with BLE advertising used for data transmission.

Sensortag battery life is not perfect.
This mode uses BLE advertising packets for useful information.

Manufacturer specific advertising data part is updated with temperature, humidity and battery level. Also cyclic auto-incremented counter is transmitted to allow for failed attempts counting.

Listening service on linux listens for advertising and updates thingspeak.com database.

Project structure:

-app 
-- files - files to replace original from sensortag application.
   Sensortag application needs to be recompiled and reloaded to sensortag h/w.
-daemon
-- linux daemon to enable listening service. Calls script. Can be added to default start during bootup to allow auto-discovery.
-script
-- python script to listen for BT advertisement. Require bluez-bluepy library.
