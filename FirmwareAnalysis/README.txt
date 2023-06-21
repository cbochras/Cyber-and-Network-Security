Firmware Analysis Toolkit (FAT henceforth) is based on Firmadyne with some changes. Firmadyne uses a PostgreSQL database to store information about the emulated images. However just for the core functionality i.e. emulating firmware, PostgreSQL is not really needed. Hence FAT doesn't use it.

Setup instructions
FAT is developed in Python 3. However you need to have both Python 3 and Python 2 installed since parts of Firmadyne and its dependencies use Python 2. It's highly recommended to install FAT inside a Virtual Machine.

To install just clone the repository and run the script ./setup.sh.

git clone https://github.com/attify/firmware-analysis-toolkit
cd firmware-analysis-toolkit
./setup.sh
After installation is completed, edit the file fat.config and provide the sudo password as shown below. Firmadyne requires sudo privileges for some of its operations. The sudo password is provided to automate the process.

[DEFAULT]
sudo_password=attify123
firmadyne_path=/home/attify/firmadyne
Running FAT
$ ./fat.py <firmware file>
Provide the firmware filename as an argument to the script.

The script would display the IP addresses assigned to the created network interfaces. Note it down.

Finally, it will say that running the firmware. Hit ENTER and wait until the firmware boots up. Ping the IP which was shown in the previous step, or open in the browser.

Congrats! The firmware is finally emulated.

To remove all analyzed firmware images, run

$ ./reset.py