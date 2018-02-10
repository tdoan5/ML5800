# ML5800

## How to connect to Erdos

### 1. On your computer
Open Terminal and enter:

#### `ssh your_account@erdos.dsm.fordham.edu` 

Enter password to connect to the Erdos server.

### 2. On Erdos

Enter follow command:

#### `jupyter-notebook --no-browser --port=8889`

The notebook app will open with an `available port` (port 8889 is available in this case) and give you a `token` to connect to server from your browser on your local computer:

![screenshot](https://github.com/tdoan5/ML5800/blob/master/port8889_snapshot.png)

If the `port 8889 is already in use`, the notebook app will automatically try `another available port`, in below example, it uses `port number 8891`, and also give you a `token` to connect to server.

![screenshot](https://github.com/tdoan5/ML5800/blob/master/port8891_snapshot.png)

