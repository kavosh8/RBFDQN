Instructions: <br />
<br />
I highly recommend using Anaconda for creating and managing virtual environments. You can download Anaconda distribution from [here](https://www.anaconda.com/distribution/#download-section). Download and install the Python 3.7 version.<br />
<br />
We now need to create an Anaconda virtual environment. We also need to specify the version of Python used for our new environment. I strongly recommend using Python 3.5.6 for this project. I also recommend choosing a descriptive name for your virtual environment, such as RBFDQN_env. On Mac, open a terminal tab. You can create such a virtual environment using the following command:<br />
conda create -n RBFDQN_env python=3.5.6 anaconda <br />
<br />
Before installing Python packages, you need to install Mujoco. The first step is to download Mujoco itself from [here](https://www.roboti.us/index.html). I highly recommend that you download mjpro131. You need to create a folder using the following command:<br />
mkdir ~/.mujoco/ <br />
<br />
Now put mjpro131 in the mujoco folder you just created. Note that you also need to get a Mujoco key and put the key inside the mujoco folder. You can get the key using one of the several ways outlined [here](https://www.roboti.us/license.html).<br />
<br />
You now want to activate your Anaconda virtual environment, and install relevant packages. To do so, use the following command:<br />
source activate RBFDQN_env <br />
<br />
The last line on your terminal should now be starting with (RBFDQN_env). This tells you that the environment is activated. You can always deactivate the environment using the command:<br />
conda deactivate <br />
<br />
You now need to install Open AI Gym. To do so, use the following command:<br />
pip install gym[all]==0.9.1<br />
<br />
Based on my experience, this step can be a bit tricky, and you may encounter a few errors. First you may not be using the right pip. To ensure that you do, find pip’s path in your virtual environment. For example, for me the path is the following:~/.conda/envs/RBFDQN_env/bin/pip. So I use the command:<br />
~/.conda/envs/RBFDQN_env/bin/pip install gym[all]==0.9.1 <br />
<br />
Additionally, you might get errors that have to do with your gcc. While I cannot recommend a one-size-fit-all solution, I found that running this command solved the problem in some cases:<br />
MACOSX_DEPLOYMENT_TARGET=10.13  ~/.conda/envs/RBFDQN_env/bin/pip install gym[all]==0.9.1 <br />
<br />
Finally, you need to install some additional python packages, namely Tensorflow, Keras, and tqdm:<br />
~/.conda/envs/RBFDQN_env/bin/pip install tensorflow==1.13.1 <br />
~/.conda/envs/RBFDQN_env/bin/pip install keras==2.1.2 <br />
~/.conda/envs/RBFDQN_env/bin/pip install tqdm <br />
<br />
Congratulations! You are now ready to run RBFDQN. Use the following command to run RBFDQN on Pendulum. It may take a few seconds for learning to kick off. <br />
python RBFDQN.py --env Pendulum-v0 --seed 0  <br />
<br />
You can choose from various domains: Pendulum-v0, LunarLanderContinuous-v2, BipedalWalker-v2, Ant-v1, HalfCheetah-v1, Hopper-v1, InvertedDoublePendulum-v1, InvertedPendulum-v1, and Reacher-v1 .Also, unless you now what you are doing, seed number can be 0. <br />