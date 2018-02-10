## ML5800

### I) How to connect to Erdos? 

#### 1. On your computer
Open Terminal and enter:

##### `ssh your_account@erdos.dsm.fordham.edu` 

Enter password to connect to the Erdos server.

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

On your computer: `ctrl + C` to clost the SSH tunnerl.


## II) How to run graphical programs remotely from the Erdos server?

