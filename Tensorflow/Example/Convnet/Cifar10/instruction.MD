
## Run Cifar10 TensorFlow tutorial on Erdos

1. Log into Erdos:

`ssh username@erdos.dsm.fordham.edu`

Enter your password.

2. Copy necessary files:

`cp `


We will open 3 different terminals to login into Erdos:

1. In the 1st terminal, run: 

`python3 cifar10_train.py`

2. In the 2nd terminal, run:

`python3 cifar10_eval.py`

We can see that the total lost decreases and the precision increases in 2 different terminals.

3. `Optional`, if you want to see in TensorBoard how lost and precision update lively over the training time.

To see how the lost updates in TensorBoard, use the 3rd terminal logged into Erdos and run:

`tensorboard --logdir /tmp/cifar10_train`

Or you want to see how the precision updates:

`tensorboard --logdir /tmp/cifar10_eval`

4. `Optional`, if you do run the step 3.

Use secure shell to see TensorBoad running on Erdos from your local computer/laptop:

`ssh -N -L 16606:localhost:6006 username@erdos.dsm.fordham.edu`

Enter your password. 

If it doesn't show any error, the tunnel is established succesfully. If you want to close the tunnel, hit `Ctrl + C`.

Open a browser in your computer/laptop and enter into the address bar:

`localhost:16006`
