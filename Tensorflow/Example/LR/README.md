### Logistic Regression with TensorFlow

##### 1. Login into the Erdos server

##### For Max OS users:

Open Terminal and enter:

`ssh username@erdos.storm.dsm.edu`

##### For Windows users:

You can use any SSH clients, such as Putty or MobaXterm.

Example how to use MobaXterm here: 

https://github.com/tdoan5/ML5800/blob/master/README.md


##### 2. Copy all necessary files for our example:

On Erdos, run the following command,

`cp -r /u/erdos/csga/doan/Public/tf/.  ~/tfML5800/`

this command creates a folder named `tfML5800` in your home directory, and copy all necessary files into it.

##### 3. Go into the *tfML5800* folder that you created:

`cd ~/tfML5800`

##### 4. Go over the Tensorflow code:

`less tflogistic.py`

You can arrow keys to read the file.

Hit `q` when you want to quit reading.

##### 5. Start iPython3 interactive shell:

`ipython3`

##### 6. Run the *tflogistic.py* or *tflogistic.ipynb*:

`run tflogistic.py`

or

`run tflogistic.ipynb`

##### 7. Quit iPython3 interactive shell:

`Ctrl+D` double times

or 

`quit`

##### 8. You also can run the Python file outside of iPython interactive shell:

`python3 tflogistic.py`
