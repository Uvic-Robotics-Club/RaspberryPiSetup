Run the Bash script in this directory named wifisetup.sh. It should open /etc/wpa_supplicant/wpa_supplicant.conf in Nano for you.
Add the network's name, password, and (optional) nickname in the format shown below (in a NEW "network" field). Then reboot the Pi (sudo reboot) and call 'ping google.com' to test the connection.

Example:

network = {
  ssid="WifiNetworkName"
  psk="Password"
  id_str="NetworkNickname"
}

If your Wi-Fi network has no password, do this instead:

network = {
  ssid="WifiNetworkName"
  key_mgmt=NONE
  id_str="NetworkNickname"
}

NOTE: After updating the network settings as described above, it is likely that 
when `wpa_supplicant` is run after saving those changes, an error will occur that 
prompts you to delete certain files, or modify a file so that changing networks 
is possible. 

If that happens, follow the instructions. Regardless, once the Pi has started up 
once successfully on a newly configured network, the errors will not persist and 
the Pi can be restarted without any network issues.