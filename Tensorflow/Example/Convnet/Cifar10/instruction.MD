
## Run Cifar10 TensorFlow tutorial on Erdos

We will open 3 different terminals to login into Erdos:

1. In the 1st terminal, run: 

`python3 cifar10_train.py`

2. In the 2nd terminal, run:

`python3 cifar10_eval.py`

We can see that the total lost decreases and precision increases over training time in 2 different terminals.

3. Optional, if you want to see in TensorBoard how lost and precision update lively over the training time.

To see lost in TensorBoard:

`tensorboard --logdir /tmp/cifar10_train`

To see precision in TensorBoard:

`tensorboard --logdir /tmp/cifar10_eval`

4. Use secure shell to see TensorBoad running on Erdos:

`ssh -N -L 16606:localhost:6006 username@erdos.dsm.fordham.edu`

Open a browser in your computer and enter into the address bar:

`localhost:16006`
