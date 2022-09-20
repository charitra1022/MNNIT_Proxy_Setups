# MNNIT_Proxy_Setups
Setup Proxy for terminals and more difficult places! (which are not directly accessible!)

Updates to this repo is welcome! Please create a **PR** to merge changes, or open an **Issue** to help us add more data to this repo!


## Quick Access
  - [Windows 11](#windows-11)
  - [Windows 10](#windows-10)
  - [Ubuntu](#ubuntu)
  - [Git](#git)

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
