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

##### 4. Next, you can run one of those following to see result:

!Note: it takes about 30-60sec to run.

For Stochastic GD:

`python3 tflogistic_SGD.py`

For Batch GD:

`python3 tflogistic_Batch.py`

##### 5. Or you also can start iPython3 interactive shell:

`ipython3`

then run following commands in the iPython3 interactive shell:

For Stochastic GD:

`run tflogistic_SGD.py`

For Batch GD:

`run tflogistic_Batch.py`

