# TF-rex
In this project we play Google's T-rex game using Reinforcement Learning.
The RL algorithm is based on the Deep Q-Learning algorithm [1] and will be implemented in TensorFlow.

### Dependencies
 - Pillow 4.3.0
 - scipy 0.19.1
 - tensorflow 1.3.0
 - optional: tensorboard


### Setup

For Debian, Ubuntu, and Ubuntu-based distros.

Start by cloning the repositery
```sh
$ git clone https://github.com/vdutor/TF-rex
```

We recommend creating a virtualenv before installing the required packages. See virtualenv or virtualenv-wrapper on how to do so.
The dependencies can be easly obtained using pip.
```sh
$ pip install -r requirements.txt
```

A simple webserver is needed to run the T-rex game
```sh
$ sudo apt install apache2
$ cd /var/www
$ sudo rm -r html
$ sudo ln -s /path/to/project/TF-Rex/t-rex-runner html
```
The game is now accessable on your localhost `127.0.0.1`. We recommend using the Google Chrome or the Mozilla Firefox browsers.   

Finally, just run the the python code
```sh
$ python main.py --help
$ python main.py --logdir logs                        # will train a model
$ python main.py --notraining --logdir trained-model  # will play with existing model, stored in `trained-model` directory.
```
While training, a different terminal can be opended to launch tensorboards
```sh
$ tensorboard --logdir logs
```
The tensorboards will be visible on `http://127.0.0.1:6006/`.

### References
[1] [Playing Atari with Deep Reinforcement Learning](https://www.cs.toronto.edu/~vmnih/docs/dqn.pdf)


### TODO
- add Q values as summary histograms in tensorboard
- try different reward functions
