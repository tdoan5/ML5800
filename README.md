## ML5800

### I) Connection Using Secure Shell

#### 1. On your computer

**`Mac OS X`**:

Open Terminal and enter:

###### `ssh your_account@erdos.dsm.fordham.edu` 

Enter password to connect to the Erdos server.

**`Windows`**:

You can use any SSH client. For our class, we will use MobaXterm Home Edition

https://mobaxterm.mobatek.net/download.html

1. Click **Session**

2. Click **SSH** in *Session settings*

3. Click **Advanced SSH settings**

4. Enter **Remote host**: `erdos.dsm.fordham.edu`

5. **Specify username**: your erdos username

6. **Port**: 22

7. Hit **OK**

<img src="https://github.com/tdoan5/ML5800/blob/master/MobaXterm_Session.PNG" width="630" height="344">

#### 2. On Erdos

Enter follow command:

###### `jupyter-notebook --no-browser --port=8889`


* The notebook app will open with an `available port` (port 8889 is available in the below snapshot), and give you a `token` to connect to server from your browser on your local computer:


![screenshot](https://github.com/tdoan5/ML5800/blob/master/port8889_snapshot.png)


* If the `port 8889 is already in use`, the notebook app will automatically try `another available port`, in the below snapshot, it uses `port number 8891`, and also give you a `token` to connect to server.


![screenshot](https://github.com/tdoan5/ML5800/blob/master/port8891_snapshot.png)

#### 3. On your computer:

Open terminal on your computer and enter follow command:

<img src="https://github.com/tdoan5/ML5800/blob/master/ssh_f_jpn.png" width="700" height="30">

with    

`port`        : the port number you see when opening the notebook app on Erdos.

`your_account`: your Erdos username.

for example: if my jupyter notebook app opens on Erdos with port `8891`, I will enter on my local computer:

###### `ssh -N -L localhost:8886:localhost:8891 tdoan5@erdos.dsm.fordham.edu` 

Option `-N` tells SSH that no remote commands will be executed, and is useful for port forwarding. 

Option `-L` lists the port forwarding configuration (remote port 8891 to local port 8886).

#### 4. Remote access from your computer to Jupyter Notebook running on Erdos

Next step, open your browser in your local computer and enter:

###### `localhost:8886`

It will ask you to put the `token` to access remotely to the notebook app on Erdos.

Go back to Erdos, copy the `token` and paste into your browser on your local computer.

!Voila.

#### 5. Close Jupyter Notebook app on Erdos and the SSH tunnel from your computer

On Erdos: `ctrl + C` 2 times to close the notebook app and all kernels.

On your computer: `ctrl + C` to clost the SSH tunnel.


## II) Remote Desktop Connection

### Mac OS X

1. Install XQuartz on your Mac, which is the official X server software for Mac

https://www.xquartz.org/

2. Install X2GO client

https://code.x2go.org/releases/binary-macosx/x2goclient/releases/4.1.1.0/

### Windows

Install X2GO client

https://code.x2go.org/releases/binary-win32/x2goclient/releases/4.1.0.0-2017.03.11/

**Use X2Go client to remote desktop connect to Erdos**

<img src="https://github.com/tdoan5/ML5800/blob/master/x2go.png" width="590" height="500">

## III) Run graphical programs remotely

Graphical program will not run as smooth as the method I.

### Mac OS X

1. Install XQuartz on your Mac, which is the official X server software for Mac

https://www.xquartz.org/

2. Run `Applications > Utilities > XQuartz.app`

3. In your Terminal, `ssh` into the linux system to log into Erdos:

######         `ssh -Y username@erdos.dsm.fordham.edu`

4. Once you are logged into the linux system, you can just run:

######         `jupyter-notebook`


### Windows

1. Install MobaXterm on your Windows

https://mobaxterm.mobatek.net/download.html

2. Run MobaXterm

3. Create a new session with X11 forwarding enable (see snapshot in the first method) 

4. Once you are logged into the linux system, you can run:

######         `jupyter-notebook`




