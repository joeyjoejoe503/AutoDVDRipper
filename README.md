Connect DVD R/W drive to an available USB port and open a terminal. Follow these steps in order will ensure a problem free install. 


Sudo apt install cifs-utils lsscsi -y 

Lsscsi -g

**Should display DVD drive with two locations like /dev/sr0  and /dev/sg0.  These are needed for later

**Make directory for saving the rips (I set mine up as a samba share also) 

curl -fsSL https://get.docker.com -o get-docker.sh 

Sh get-docker.sh 

Sudo systemctl enable docker 

Sudo systemctl start docker 

Nano makemkv.sh 

**Use the script makemkv.sh file make sure to replace the DVD location with the ones you found earlier (device /dev/sg3 \) and replace the (/mnt/Nas) with your file saving directory you created earlier. 

Sudo chmod +x ./makemkv.sh 

Sudo ./makemkv.sh 

**Go to a web browser and input your IP address:5800 

**Make mkv should be open and have your DVD drive listed in the web UI. 

Sudo nano /etc/systemd/system/docker-makemkv.service 

**Now create the docker-makemkv.service file

Sudo systemctl enable docker-makemkv.service 

You are all set. The dvd ripper should automatically start and rip the dvd whenever a new disc is inserted. Also the services will automatically start everytime your system reboots.
