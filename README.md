{\rtf1\ansi\ansicpg1252\cocoartf1671\cocoasubrtf200
{\fonttbl\f0\fswiss\fcharset0 Helvetica;}
{\colortbl;\red255\green255\blue255;\red0\green0\blue0;\red255\green255\blue255;\red0\green0\blue0;
\red255\green255\blue255;\red11\green38\blue81;\red27\green31\blue35;\red21\green24\blue26;\red17\green85\blue185;
}
{\*\expandedcolortbl;;\cssrgb\c0\c1\c1;\cssrgb\c100000\c100000\c99985;\cssrgb\c0\c1\c1;
\cssrgb\c100000\c100000\c99985;\cssrgb\c3352\c20749\c39038;\cssrgb\c14207\c16177\c18085;\cssrgb\c10657\c12234\c13762\c29804;\cssrgb\c6057\c42307\c77536;
}
\margl1440\margr1440\vieww17680\viewh14720\viewkind0
\pard\tx720\tx1440\tx2160\tx2880\tx3600\tx4320\tx5040\tx5760\tx6480\tx7200\tx7920\tx8640\pardirnatural\partightenfactor0

\f0\fs36 \cf2 \cb3 Instructions: <br />\
\pard\tx720\tx1440\tx2160\tx2880\tx3600\tx4320\tx5040\tx5760\tx6480\tx7200\tx7920\tx8640\pardirnatural\partightenfactor0
\cf4 \cb5 <br />\cf2 \cb3 \
I highly recommend using Anaconda for creating and managing virtual environments. You can download Anaconda distribution from [here](https://www.anaconda.com/distribution/#download-section). Download and install the Python 3.7 version.\cf4 \cb5 <br />\cf2 \cb3 \
\cf4 \cb5 <br />\cf2 \cb3 \
We now need to create an Anaconda virtual environment. We also need to specify the version of Python used for our new environment. I strongly recommend using Python 3.5.6 for this project. I also recommend choosing a descriptive name for your virtual environment, such as RBFDQN_env. On Mac, open a terminal tab. You can create such a virtual environment using the following command:\cf4 \cb5 <br />\cf2 \cb3 \
conda create -n RBFDQN_env python=3.5.6 anaconda \cf4 \cb5 <br />\
<br />\cf2 \cb3 \
Before installing Python packages, you need to install Mujoco. The first step is to download Mujoco itself from [here](https://www.roboti.us/index.html). I highly recommend that you download mjpro131. You need to create a folder using the following command:\cf4 \cb5 <br />\cf2 \cb3 \
mkdir ~/.mujoco/ \cf4 \cb5 <br />\cf2 \cb3 \
\cf4 \cb5 <br />\cf2 \cb3 \
Now put mjpro131 in the mujoco folder you just created. Note that you also need to get a Mujoco key and put the key inside the mujoco folder. You can get the key using one of the several ways outlined [here](https://www.roboti.us/license.html).\cf4 \cb5 <br />\cf2 \cb3 \
\cf4 \cb5 <br />\cf2 \cb3 \
You now want to activate your Anaconda virtual environment, and install relevant packages. To do so, use the following command:\cf4 \cb5 <br />\cf2 \cb3 \
source activate RBFDQN_env \cf4 \cb5 <br />\cf2 \cb3 \
\cf4 \cb5 <br />\cf2 \cb3 \
The last line on your terminal should now be starting with (RBFDQN_env). This tells you that the environment is activated. You can always deactivate the environment using the command:\cf4 \cb5 <br />\cf2 \cb3 \
conda deactivate \cf4 \cb5 <br />\cf2 \cb3 \
\cf4 \cb5 <br />\cf2 \cb3 \
You now need to install Open AI Gym. To do so, use the following command:\cf4 \cb5 <br />\cf2 \cb3 \
\pard\pardeftab720\partightenfactor0
\cf2 \cb3 \expnd0\expndtw0\kerning0
pip install gym[all]==0.9.1\cf4 \cb5 \kerning1\expnd0\expndtw0 <br />\
\pard\tx720\tx1440\tx2160\tx2880\tx3600\tx4320\tx5040\tx5760\tx6480\tx7200\tx7920\tx8640\pardirnatural\partightenfactor0
\cf4 <br />\cf2 \cb3 \expnd0\expndtw0\kerning0
\
\pard\pardeftab720\partightenfactor0
\cf2 Based on my experience, this step can be a bit tricky, and you may encounter a few errors. First you may not be using the right pip. To ensure that you do, find pip\'92s path in your virtual environment. For example, for me the path is the following:\cf2 \cb3 \kerning1\expnd0\expndtw0 \CocoaLigature0 ~/.conda/envs/RBFDQN_env/bin/pip. So I use the command:\cf4 \cb5 \CocoaLigature1 <br />\cf2 \cb3 \CocoaLigature0 \
~/.conda/envs/RBFDQN_env/bin/pip\cf2 \cb3 \expnd0\expndtw0\kerning0
\CocoaLigature1  install gym[all]==0.9.1 \cf4 \cb5 \kerning1\expnd0\expndtw0 <br />\cf2 \cb3 \expnd0\expndtw0\kerning0
\
\pard\tx720\tx1440\tx2160\tx2880\tx3600\tx4320\tx5040\tx5760\tx6480\tx7200\tx7920\tx8640\pardirnatural\partightenfactor0
\cf4 \cb5 \kerning1\expnd0\expndtw0 <br />\cf2 \cb3 \expnd0\expndtw0\kerning0
\
\pard\pardeftab720\partightenfactor0
\cf2 Additionally, you might get errors that have to do with your gcc. While I cannot recommend a one-size-fit-all solution, I found that running this command solved the problem in some cases:\cf4 \cb5 \kerning1\expnd0\expndtw0 <br />\cf2 \cb3 \
\cf2 \cb3 \expnd0\expndtw0\kerning0
MACOSX_DEPLOYMENT_TARGET=10.13  \cf2 \cb3 \kerning1\expnd0\expndtw0 \CocoaLigature0 ~/.conda/envs/RBFDQN_env/bin/pip\cf2 \cb3 \expnd0\expndtw0\kerning0
\CocoaLigature1  install gym[all]==0.9.1 \cf4 \cb5 \kerning1\expnd0\expndtw0 <br />\cf2 \cb3 \
\pard\tx720\tx1440\tx2160\tx2880\tx3600\tx4320\tx5040\tx5760\tx6480\tx7200\tx7920\tx8640\pardirnatural\partightenfactor0
\cf4 \cb5 <br />\cf2 \cb3 \expnd0\expndtw0\kerning0
\
\pard\pardeftab720\partightenfactor0
\cf2 Finally, you need to install some additional python packages, namely Tensorflow, Keras, and tqdm:\cf4 \cb5 \kerning1\expnd0\expndtw0 <br />\cf2 \cb3 \expnd0\expndtw0\kerning0
\
\pard\tx560\tx1120\tx1680\tx2240\tx2800\tx3360\tx3920\tx4480\tx5040\tx5600\tx6160\tx6720\pardirnatural\partightenfactor0
\cf2 \cb3 \kerning1\expnd0\expndtw0 \CocoaLigature0 ~/.conda/envs/RBFDQN_env/bin/pip install tensorflow==1.13.1 \cf4 \cb5 \CocoaLigature1 <br />\cf2 \cb3 \CocoaLigature0 \
~/.conda/envs/RBFDQN_env/bin/pip install keras==2.1.2 \cf4 \cb5 \CocoaLigature1 <br />\cf2 \cb3 \CocoaLigature0 \
~/.conda/envs/RBFDQN_env/bin/pip install tqdm \cf4 \cb5 \CocoaLigature1 <br />\cf2 \cb3 \CocoaLigature0 \
\pard\tx720\tx1440\tx2160\tx2880\tx3600\tx4320\tx5040\tx5760\tx6480\tx7200\tx7920\tx8640\pardirnatural\partightenfactor0
\cf4 \cb5 \CocoaLigature1 <br />\cf2 \cb3 \CocoaLigature0 \
\pard\tx560\tx1120\tx1680\tx2240\tx2800\tx3360\tx3920\tx4480\tx5040\tx5600\tx6160\tx6720\pardirnatural\partightenfactor0
\cf2 Congratulations! You are now ready to run RBFDQN. Use the following command to run RBFDQN on Pendulum. It may take a few seconds for learning to kick off. \cf4 \cb5 \CocoaLigature1 <br />\cf2 \cb3 \CocoaLigature0 \
python RBFDQN.py --env Pendulum-v0 --seed 0  \cf4 \cb5 \CocoaLigature1 <br />\cf2 \cb3 \CocoaLigature0 \
\pard\tx720\tx1440\tx2160\tx2880\tx3600\tx4320\tx5040\tx5760\tx6480\tx7200\tx7920\tx8640\pardirnatural\partightenfactor0
\cf4 \cb5 \CocoaLigature1 <br />\cf2 \cb3 \CocoaLigature0 \
\pard\tx560\tx1120\tx1680\tx2240\tx2800\tx3360\tx3920\tx4480\tx5040\tx5600\tx6160\tx6720\pardirnatural\partightenfactor0
\cf2 You can choose from various domains: \cf2 \cb3 \expnd0\expndtw0\kerning0
\CocoaLigature1 Pendulum-v0, \cf2 \cb3 LunarLanderContinuous-v2, BipedalWalker-v2, Ant-v1, HalfCheetah-v1, Hopper-v1, InvertedDoublePendulum-v1, InvertedPendulum-v1, and Reacher-v1 .Also, unless you now what you are doing, seed number can be 0. \cf4 \cb5 \kerning1\expnd0\expndtw0 <br />\cf2 \cb3 \expnd0\expndtw0\kerning0
\

\itap1\trowd \taflags1 \trgaph108\trleft-108 \trbrdrt\brdrnil \trbrdrl\brdrnil \trbrdrr\brdrnil 
\clvertalt \clshdrawnil \clwWidth1000\clftsWidth3 \clminw1000 \clbrdrt\brdrnil \clbrdrl\brdrnil \clbrdrb\brdrnil \clbrdrr\brdrnil \clpadl200 \clpadr200 \gaph\cellx4320
\clvertalt \clshdrawnil \clwWidth22796\clftsWidth3 \clbrdrt\brdrnil \clbrdrl\brdrnil \clbrdrb\brdrnil \clbrdrr\brdrnil \clpadl200 \clpadr200 \gaph\cellx8640
\pard\intbl\itap1\pardeftab720\partightenfactor0
\cf2 \cb3 \cell 
\pard\intbl\itap1\pardeftab720\partightenfactor0
\cf2 \cb3 \cell \row

\itap1\trowd \taflags1 \trgaph108\trleft-108 \trbrdrl\brdrnil \trbrdrr\brdrnil 
\clvertalt \clshdrawnil \clwWidth1000\clftsWidth3 \clminw1000 \clbrdrt\brdrnil \clbrdrl\brdrnil \clbrdrb\brdrnil \clbrdrr\brdrnil \clpadl200 \clpadr200 \gaph\cellx4320
\clvertalt \clshdrawnil \clwWidth22796\clftsWidth3 \clbrdrt\brdrnil \clbrdrl\brdrnil \clbrdrb\brdrnil \clbrdrr\brdrnil \clpadl200 \clpadr200 \gaph\cellx8640
\pard\intbl\itap1\pardeftab720\partightenfactor0
\cf2 \cb3 \cell 
\pard\intbl\itap1\pardeftab720\partightenfactor0
\cf2 \cb3 \cell \row

\itap1\trowd \taflags1 \trgaph108\trleft-108 \trbrdrl\brdrnil \trbrdrr\brdrnil 
\clvertalt \clshdrawnil \clwWidth1000\clftsWidth3 \clminw1000 \clbrdrt\brdrnil \clbrdrl\brdrnil \clbrdrb\brdrnil \clbrdrr\brdrnil \clpadl200 \clpadr200 \gaph\cellx4320
\clvertalt \clshdrawnil \clwWidth22796\clftsWidth3 \clbrdrt\brdrnil \clbrdrl\brdrnil \clbrdrb\brdrnil \clbrdrr\brdrnil \clpadl200 \clpadr200 \gaph\cellx8640
\pard\intbl\itap1\pardeftab720\partightenfactor0
\cf2 \cb3 \cell 
\pard\intbl\itap1\pardeftab720\partightenfactor0
\cf2 \cb3 \cell \row

\itap1\trowd \taflags1 \trgaph108\trleft-108 \trbrdrl\brdrnil \trbrdrr\brdrnil 
\clvertalt \clshdrawnil \clwWidth1000\clftsWidth3 \clminw1000 \clbrdrt\brdrnil \clbrdrl\brdrnil \clbrdrb\brdrnil \clbrdrr\brdrnil \clpadl200 \clpadr200 \gaph\cellx4320
\clvertalt \clshdrawnil \clwWidth22796\clftsWidth3 \clbrdrt\brdrnil \clbrdrl\brdrnil \clbrdrb\brdrnil \clbrdrr\brdrnil \clpadl200 \clpadr200 \gaph\cellx8640
\pard\intbl\itap1\pardeftab720\partightenfactor0
\cf2 \cb3 \cell 
\pard\intbl\itap1\pardeftab720\partightenfactor0
\cf2 \cb3 \cell \row

\itap1\trowd \taflags1 \trgaph108\trleft-108 \trbrdrl\brdrnil \trbrdrr\brdrnil 
\clvertalt \clshdrawnil \clwWidth1000\clftsWidth3 \clminw1000 \clbrdrt\brdrnil \clbrdrl\brdrnil \clbrdrb\brdrnil \clbrdrr\brdrnil \clpadl200 \clpadr200 \gaph\cellx4320
\clvertalt \clshdrawnil \clwWidth22796\clftsWidth3 \clbrdrt\brdrnil \clbrdrl\brdrnil \clbrdrb\brdrnil \clbrdrr\brdrnil \clpadl200 \clpadr200 \gaph\cellx8640
\pard\intbl\itap1\pardeftab720\partightenfactor0
\cf2 \cb3 \cell 
\pard\intbl\itap1\pardeftab720\partightenfactor0
\cf2 \cb3 \cell \row

\itap1\trowd \taflags1 \trgaph108\trleft-108 \trbrdrl\brdrnil \trbrdrr\brdrnil 
\clvertalt \clshdrawnil \clwWidth1000\clftsWidth3 \clminw1000 \clbrdrt\brdrnil \clbrdrl\brdrnil \clbrdrb\brdrnil \clbrdrr\brdrnil \clpadl200 \clpadr200 \gaph\cellx4320
\clvertalt \clshdrawnil \clwWidth22796\clftsWidth3 \clbrdrt\brdrnil \clbrdrl\brdrnil \clbrdrb\brdrnil \clbrdrr\brdrnil \clpadl200 \clpadr200 \gaph\cellx8640
\pard\intbl\itap1\pardeftab720\partightenfactor0
\cf2 \cb3 \cell 
\pard\intbl\itap1\pardeftab720\partightenfactor0
\cf2 \cb3 \cell \row

\itap1\trowd \taflags1 \trgaph108\trleft-108 \trbrdrl\brdrnil \trbrdrr\brdrnil 
\clvertalt \clshdrawnil \clwWidth1000\clftsWidth3 \clminw1000 \clbrdrt\brdrnil \clbrdrl\brdrnil \clbrdrb\brdrnil \clbrdrr\brdrnil \clpadl200 \clpadr200 \gaph\cellx4320
\clvertalt \clshdrawnil \clwWidth22796\clftsWidth3 \clbrdrt\brdrnil \clbrdrl\brdrnil \clbrdrb\brdrnil \clbrdrr\brdrnil \clpadl200 \clpadr200 \gaph\cellx8640
\pard\intbl\itap1\pardeftab720\partightenfactor0
\cf2 \cb3 \cell 
\pard\intbl\itap1\pardeftab720\partightenfactor0
\cf2 \cb3 \cell \row

\itap1\trowd \taflags1 \trgaph108\trleft-108 \trbrdrl\brdrnil \trbrdrt\brdrnil \trbrdrr\brdrnil 
\clvertalt \clshdrawnil \clwWidth1000\clftsWidth3 \clminw1000 \clbrdrt\brdrnil \clbrdrl\brdrnil \clbrdrb\brdrnil \clbrdrr\brdrnil \clpadl200 \clpadr200 \gaph\cellx4320
\clvertalt \clshdrawnil \clwWidth22796\clftsWidth3 \clbrdrt\brdrnil \clbrdrl\brdrnil \clbrdrb\brdrnil \clbrdrr\brdrnil \clpadl200 \clpadr200 \gaph\cellx8640
\pard\intbl\itap1\pardeftab720\partightenfactor0
\cf2 \cb3 \cell 
\pard\intbl\itap1\pardeftab720\partightenfactor0
\cf2 \cb3 \cell \lastrow\row
}