# MNNIT_Proxy_Setups
Setup Proxy for terminals and more difficult places! (which are not directly accessible!)

Updates to this repo is welcome! Please create a **PR** to merge changes, or open an **Issue** to help us add more data to this repo!


## Quick Access
  - [Windows 11](#windows-11)
  - [Windows 10](#windows-10)
  - [Windows Applications (Proxifier)](#windows-applications)
  - [Ethernet Connection (Windows)](#ethernet-connection-windows)
  - [Ubuntu](#ubuntu)
  - [Git](#git)
  - [Linux Terminal](#linux-terminal)
  - [MSYS2](#msys2)
  - [Node](#node)
  - [Pip - Python](#pip---python)

<hr>

## Windows 11
**Settings** > **Network & Internet** > **Proxy** > **Manual proxy setup** > **Edit**

1. Toggle **Use a proxy server** to **On**
2. Proxy IP address - ```172.31.102.29```
3. Port - ```3128```
4. Click **Save**

<hr>

## Windows 10
**Settings** > **Network & Internet** > **Proxy** > **Manual proxy setup**

1. Toggle **Use a proxy server** to **On**
2. Address - ```172.31.102.29```
3. Port - ```3128```
4. Click **Save**

<hr>

## Windows Applications
**To run different applications on windows you have to install PROXIFIER**

1. Download & Install [**Proxifier**]("https://www.proxifier.com/download/)"
2. Setup proxifier based on the following [instructions](https://cc-mnnit.github.io/proxy-settings/proxifier/).

<hr>

## Ethernet Connection (Windows)
### For Windows 11
**Settings** > **Network & Internet** > **Ethernet**

1. Click on **Edit** button next to **IP Assignment**.
2. Choose **Manual**.
3. Enable **IPv4**.
4. Check the network configuration details for your location (hostel/department) [here](https://mnnit.ac.in/computercentre/index.php/ip-address-scheme):
    - IP Address - Based on your allocated range
    - Subnet Mask - As specified for your location
    - Gateway - As specified for your location
    - Preferred DNS - `172.31.100.7`
    - Alternate DNS - `172.31.100.8`
5. Click on **Save**.

Make sure to set up the proxy using the steps mentioned [here](#windows-11) or use [Proxifier](#windows-applications) to run applications. 

**Note**: 
- Each hostel, department, and location has its specific network configuration
- The IP address must be unique and not used by any other device on the network
- In case of IP conflict, try a different number within your allocated range

<hr>

## Ubuntu
**Settings** > **Network** > **Network Proxy**

1. Click on **Gear** icon
2. Choose **Manual**
3. HTTP Proxy - ```172.31.102.29``` & ```3128```
4. HTTPS Proxy - ```172.31.102.29``` & ```3128```
5. FTP Proxy - ```172.31.102.29``` & ```3128```
6. Sockets Host - ```172.31.102.29``` & ```3128```
7. Close the pop-up.

<hr>

## Git
Open command prompt (in Windows) and run the following commands one by one

1. ```git config --global --unset-all https.proxy```
2. ```git config --global --unset-all http.proxy```
3. ```git config --global --add http.proxy http://edcguest:edcguest@172.31.102.29:3128```
4. ```git config --global --add https.proxy http://edcguest:edcguest@172.31.102.29:3128```

<hr>

## Linux Terminal
Open terminal (in Linux) and follow the steps below:

1. Run ```sudo -i```
2. Enter your root password (password is not visible while typing in linux terminal)
3. Run ```gedit /etc/apt/apt.conf```
4. Write ```Acquire::http::Proxy "http://edcguest:edcguest@172.31.102.29:3128";``` and **Save** and then **Close** the text editor
5. Run ```gedit /etc/bash.bashrc```
6. Write the following at the bottom of the file.
```
export http_proxy=http://edcguest:edcguest@172.31.102.29:3128/

export ftp_proxy=http://edcguest:edcguest@172.31.102.29:3128/

export https_proxy=https://edcguest:edcguest@172.31.102.29:3128/
```
7. **Save** and **Close** the text editor.
8. **Close** the terminal.

<hr>

## MSYS2
Open **MSYS2 MSYS** prompt (in Windows) and run the following commands one by one

### Temporary: Works on the session where the commands have been run. Needs to be run every time
```
export HTTP_PROXY="edcguest:edcguest@172.31.102.29:3128"
export HTTPS_PROXY=$HTTP_PROXY
export http_proxy=$HTTP_PROXY
export https_proxy=$HTTP_PROXY
```

### Permanent: Automatically read by the terminal on startup
1. ```vim .bashrc``` Opens the **bashrc** file. 
2. Press ```i``` and Add the following lines at the end of the file.
```
export HTTP_PROXY="edcguest:edcguest@172.31.100.25:3128"
export HTTPS_PROXY=$HTTP_PROXY
export http_proxy=$HTTP_PROXY
export https_proxy=$HTTP_PROXY
```
3. Press ```Esc``` and write ```:wq``` and press ```Enter```.

<hr>

## Node
Run these commands one by one in command prompt.
Make sure **Node is Installed** and added to path.

1. ```npm config set proxy http://edcguest:edcguest@172.31.102.29:3128```
2. ```npm config set https-proxy http://edcguest:edcguest@172.31.102.29:3128```

More help [here](https://www.jhipster.tech/configuring-a-corporate-proxy/).

To remove proxy configuration from node, run the following commands
1. ```npm config rm proxy```
2. ```npm config rm https-proxy```
3. ```npm config --global rm proxy```
4. ```npm config --global rm https-proxy```

<hr>

## Pip - Python

Installing python packages also need to have proxy setup. You can install packages behind proxy via the following hack.

```pip install --proxy http://<usr_name>:<password>@<proxyserver_name>:<port#> <pkg_name>```

Eg.

```pip install --proxy http://edcguest:edcguest@172.31.102.29:3128 djangorestframework```

> Do we need to include this long text each time? <br>
> It is recommended, as you might need to sometimes install package normally. 

To install `requirements.txt`, write the following

```pip install --proxy http://<usr_name>@<proxyserver_name>:<port#> -r requirements.txt```

Eg.

```pip install --proxy http://edcguest:edcguest@172.31.102.29:3128 -r requirements.txt```

<hr>
