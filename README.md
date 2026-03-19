# Authentication-FreeRadius
### 1. Adding the PGP Public Key
```
install -d -o root -g root -m 0755 /etc/apt/keyrings
```
```
curl -s 'https://packages.networkradius.com/pgp/packages%40networkradius.com' | \
    sudo tee /etc/apt/keyrings/packages.networkradius.com.asc > /dev/null
```
####   The Purpose:
This establishes trust. Linux packages are digitally signed. By downloading this public key and placing it in /etc/apt/keyrings, you are telling your system: "I trust any software signed by the owner of this key."


### 2. Setting APT Preferences (Pinning)
```
printf 'Package: /freeradius/\nPin: origin "packages.networkradius.com"\nPin-Priority: 999\n' | \
sudo tee /etc/apt/preferences.d/networkradius > /dev/null
```
#### The Purpose: 
This is called Apt Pinning. Ubuntu has its own version of FreeRADIUS in its default repositories. Usually, Ubuntu's version has a lower version number than the one provided directly by the developers (NetworkRADIUS).


### 3. Adding the APT Sources List
```
echo "deb [arch=amd64 signed-by=/etc/apt/keyrings/packages.networkradius.com.asc] http://packages.networkradius.com/freeradius-3.2/ubuntu/noble noble main" | \
sudo tee /etc/apt/sources.list.d/networkradius.list > /dev/null
```
#### The Purpose: 
This tells your computer where to look for the software.


### 4.  Update the APT database
~~~
sudo apt update
~~~


### 5. Installation and Dependencies
~~~
sudo apt install freeradius 
~~~
~~~
sudo apt install git libssl-dev devscripts pkg-config libnl-3-dev libnl-genl-3-dev
~~~


