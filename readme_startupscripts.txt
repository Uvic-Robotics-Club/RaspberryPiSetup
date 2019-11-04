This guide will tell you everything you need to know to get a rover brain auto-pulling from Git and running its software on startup!

First, you'll need Wi-Fi working. Consult readme_wifi.txt for a walkthrough.

Getting things to run on startup in Linux is straightforward. Just add the desired commands/script executions to .bashrc, found in the ~ directory.

You'll want to install Git. sudo apt-get install git

You'll want to clone the Scheduler repo into the root of storage.

Then in your .bashrc startup script you can add the commands "git -C ~/[path] pull" for every GitHub repo you are using. At the time of this writing, that means the Shell and RaspberryPiSetup repos. See the last bunch of lines of .bashrc_copy.

BUT .bashrc runs AFTER LOGIN! We can't have the rover requiring manual login every time the thing boots - we want it to run without any help. To make the Pi log in automatically, you'll have to use the Raspberry Pi Software Configuration Tool. Follow these steps and the Pi will be logging in without help:
sudo raspi-config
3 Boot Options
B1 Desktop/CLI
B2 Console AutoLogin

For the joystick to work, you'll need to install pygame. Follow the top answer at https://askubuntu.com/questions/401342/how-to-download-pygame-in-python3-3

You'll also need to install pyserial:
apt install python3-pip
pip3 install pyserial --user

And then you should be good to go:
python3 shell_start.py

Note: pip is for python 2, pip3 is for python 3. Similarly, you MUST call Python scripts using the python3 command rather than simply calling their names. Calling their names may attempt to run them in Python 2, which won't work.
