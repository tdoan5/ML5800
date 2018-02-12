## ML5800

The 1<sup>st</sup> connection method using *secure shell* gives the best performance when remotely access to Jupyter Notebook app on the Erdos server.

The 2<sup>nd</sup> and 3<sup>rd</sup> connection methods are more simple, but you may experience severe delay or lag. The connection performances are not as 'smooth' as the 1<sup>st</sup> method's. 

### I) Connection Using Secure Shell

#### 1. On your computer

**`Mac OS X`**:

Open Terminal and enter:

###### `ssh your_account@erdos.dsm.fordham.edu` 

Enter password to connect to the Erdos server.


**`Windows`**:

You can use any SSH client. For our class, we will use MobaXterm Home Edition (you can choose either Portable or Installer version).

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

Open a new terminal on your local computer, enter the follow command:

<img src="https://github.com/tdoan5/ML5800/blob/master/ssh_N_L.png" width="700" height="30">

with:    

`localPort`: the port you choose on your `local computer` to connect to Erdos.

`remotePort`: the port number you see when opening the notebook app on Erdos in step 2.

`your_account`: your Erdos username.

Option `-N` tells SSH that no remote commands will be executed, and it is useful for port forwarding. 

Option `-L` lists the port forwarding configuration (remote port to local port).


**for example**: if we choose `localPort` as `8880` on our computer, and the Jupyter Notebook app opens on Erdos with port `8890`, we will enter on the `local computer`:

###### `ssh -N -L localhost:8880:localhost:8890 tdoan5@erdos.dsm.fordham.edu` 


Enter the Erdos password. After entering password, it does not show anything but the tunnel is opened successfuly, you can go to step 4. Note that if you do use any port different from 8886 (e.g. port 8880 instead of 8886) for the above `ssh` command, in step 4, you have to enter `localhost:8880` in your browswer.

It prompts you to enter Erdos password. 

!Note: When you're done, you can hit `Ctrl + C` to close the tunnel.




#### 4. Remote access from your computer to Jupyter Notebook running on Erdos

Next step, open your `browser` in your local computer and enter into address bar with `local post` used in part 3:

###### `localhost:localPort`

It will ask you to put the `token` to access remotely to the notebook app on Erdos.

Go back to Erdos, copy the `token` and paste into your browser on your local computer.

!Voila.

**!Note:**

When you're done, you can close Jupyter Notebook app on Erdos and the SSH tunnel from your computer.

On Erdos: `ctrl + C` 2 times to close the notebook app and all kernels.

On your computer: `ctrl + C` to close the SSH tunnel.


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

Enter your username and password to login Erdos

<img src="https://github.com/tdoan5/ML5800/blob/master/x2go_login.png" width="410" height="350">

If it asks to unlock the keyring, enter your Erdos password again.

<img src="https://github.com/tdoan5/ML5800/blob/master/x2go_kr.png" width="350" height="112">

Hit `logout` when you complete your task.

## III) Run graphical programs remotely

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

3. Create a new session with X11 forwarding enable (see instructions in the 1<sup>st</sup> method using secure shell)

4. Enable X server, click to X server button near Exit button, it will turn Green

<img src="https://github.com/tdoan5/ML5800/blob/master/xserver.png" width="630" height="344">

5. Once you are logged into the linux system, you can run:

######         `jupyter-notebook`

