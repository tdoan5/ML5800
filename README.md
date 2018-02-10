## ML5800

### I) How to connect to Erdos? 

#### 1. On your computer

For `Mac OS X`:

Open Terminal and enter:

##### `ssh your_account@erdos.dsm.fordham.edu` 

Enter password to connect to the Erdos server.

For `Windows`:

You can use any SSH client. For our class, we will use MobaXterm Home Edition

https://mobaxterm.mobatek.net/download.html

#### 2. On Erdos

Enter follow command:

##### `jupyter-notebook --no-browser --port=8889`


* The notebook app will open with an `available port` (port 8889 is available in this case) and give you a `token` to connect to server from your browser on your local computer:


![screenshot](https://github.com/tdoan5/ML5800/blob/master/port8889_snapshot.png)


* If the `port 8889 is already in use`, the notebook app will automatically try `another available port`, in below example, it uses `port number 8891`, and also give you a `token` to connect to server.


![screenshot](https://github.com/tdoan5/ML5800/blob/master/port8891_snapshot.png)

#### 3. On your computer:

Open terminal on your computer and enter follow command:

<img src="https://github.com/tdoan5/ML5800/blob/master/ssh_jpn.png" width="800" height="40">

with    

`port`        : the port number you see when opening the notebook app on Erdos.

`your_account`: your Erdos username.

for example: if my jupyter notebook app opens on Erdos with port `8891`, I will enter on my local computer:

###### `ssh -N -f -L localhost:8886:localhost:8891 tdoan5@erdos.dsm.fordham.edu` 

#### 4. Remote access from your computer to Jupyter Notebook running on Erdos

Next step, open your browser in your local computer and enter:

##### `localhost:8886`

It will ask you to put the `token` to access remotely to the notebook app on Erdos.

Go back to Erdos, copy the `token` and paste into your browser on your local computer.

!Voila.

#### 5. Close Jupyter Notebook app on Erdo and the SSH tunnel from your computer

On Erdos: `ctrl + C` 2 times to close the notebook app and all kernels.

On your computer: `ctrl + C` to clost the SSH tunnel.


## II) How to run graphical programs remotely from the Erdos server?

### Mac OS X
__

1. Install XQuartz on your Mac, which is the official X server software for Mac

2. Run `Applications > Utilities > XQuartz.app`

3. Right click on the XQuartz icon in the dock and select `Applications > Terminal`.  This should bring up a new xterm terminal windows.

4. In this xterm windows, `ssh` into the linux system to log into Erdos:

#####         `ssh -Y username@erdos.dsm.fordham.edu`

5. Once you are logged into the linux system, you can just run:

#####         `jupyter-notebook`


### Windows

1. Install MobaXterm (or Putty) on your Windows

2. Run MobaXterm

3. Create a new session 

4. Run MobaXterm and set things up as follows:

- Enter the server name in Host Name
- Make sure the Connection type is set to SSH
- Enable X11 forwarding (Connection > SSH > X11)

5. Once you are logged into the linux system, you can run:

#####         `jupyter-notebook`




