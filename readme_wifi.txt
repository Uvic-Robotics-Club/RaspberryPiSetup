Run the Bash script in this directory named wifisetup.sh. It should open /etc/wpa_supplicant/wpa_supplicant.conf in Nano for you.
Add the network's name, password, and (optional) nickname in the format shown below (in a NEW "network" field). Then reboot the Pi (sudo reboot) and call 'ping google.com' to test the connection.

Example:

network = {
  ssid="WifiNetworkName"
  psk="Password"
  id_str="NetworkNickname"
}
