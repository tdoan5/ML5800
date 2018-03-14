
## Run Cifar10 TensorFlow tutorial on Erdos

1. Log into Erdos:

`ssh username@erdos.dsm.fordham.edu`

Enter your password.

2. On Erdos, copy necessary files:

`cp -r /u/erdos/csga/doan/Public/cifar10/. ~/tfconvnet/`

this command creates a folder named `tfconvnet` in your home directory, and copy all necessary files into that.

3. In the Terminal, run: 

`python3 ~/tfconvnet/cifar10_train.py`

It will read cifar10 data from my Public folder `/u/erdos/csga/doan/Public/cifar10_data`.

It will save training checkpoint logs to `~/tfconvnet/cifar10_train` on your Erdos account.

4. In the 2nd terminal, run:

`python3 ~/tfconvnet/cifar10_eval.py`

It will save checkpoint logs at `~/tfconvnet/cifar10_eval` on your Erdos account.

We can see that the total lost decreases and the precision increases when training in 2 different terminals.

5. `Optional`, if you want to see in TensorBoard how the lost and the precision update lively over the training time.

To see how the lost updates in TensorBoard, use the 3rd terminal logged into Erdos and run:

`tensorboard --logdir ~/tfconvnet/cifar10_train`

Or you want to see how the precision updates:

`tensorboard --logdir ~/tfconvnet/cifar10_eval`

`Note`: 

!!! Remember if you want to quit TensorBoard, hit `Ctrl + C`.


6. `Optional`, only if you do run the step 3.

Use secure shell to see TensorBoad running on Erdos from your local computer/laptop:

`ssh -N -L 16006:localhost:6006 username@erdos.dsm.fordham.edu`

Enter your password. 

If it doesn't show any error, the tunnel is established succesfully. If you want to close the tunnel, hit `Ctrl + C`.

Next, open a browser in your computer/laptop and enter into the address bar:

`localhost:16006`

You will see the TensorBoard

`Note:`

!!! Remember to close the tunnel and release the port 16006 when you complete, hit `Ctrl + C`.

Otherwise, if you run the step 6 again, it may shows error that the port is already used.

7. `Note`:

If you want to see Tensorboad, you have to do both steps 3 and 4. 

You can perform either of step 3 or 4 first, it doesn't matter.

