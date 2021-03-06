
## Installing AzureML SDK inside Anaconda Managed Environment
1.	Download Anaconda Installation kit from https://www.anaconda.com/download/:
- Windows: https://repo.anaconda.com/archive/Anaconda3-5.3.1-Windows-x86_64.exe
- Mac OS: https://repo.anaconda.com/archive/Anaconda3-5.3.1-MacOSX-x86_64.pkg 

2.	Install Anaconda followed by the instruction with default options. It may take up to 15 minutes.

3.	After Anaconda successfully installed, start “**Anaconda Navigator**” application. 
- In Windows, you should be able to search it from start bar. 
- In Mac OS, you can find it inside your Anaconda3 installation directory (by default `~/anaconda3`).

4.	Go into “**Environments**” tab, and select “**Create**” to create a new Conda environment as shown below

<img src="/1.png" alt="drawing" width="600"/>


5.	Type in “azureml” as the name. Select “**Python 3.6**” and click “**Create**”. It may take a few minutes to configure the new environment.
 
<img src="/2.png" alt="drawing" width="400"/>

6.	When the new environment is ready, choose “**Open Terminal**” to start a new terminal in that environment.
 
<img src="/3.png" alt="drawing" width="400"/>

### Note that

During ***step 5***, if you receive the following error 

```
Some of the functionality of Anaconda Navigator will be limited in offline mode.

Installation and upgrade of packages will be subject to the packages currently available on your package cache.
```
Please **Open Terminal** of **base (root)** environment. In the launched terminal, please run the following command:

```
conda create -n azureml python=3.6 anaconda
```
followed by
- Windows: ```activate azureml```
- Mac OS: ```source activate azureml```

7.	In the terminal run the below command to install AzureML SDK and other related packages used in our workshop:

```sh
pip install --upgrade azureml-sdk[notebooks,contrib] scikit-image tensorflow tensorboardX --user
```

It may take 10 more minutes to install the packages. When complete, you can do the following to check if AzureML SDK has successfully installed:

<img src="/4.png" alt="drawing" width="600"/>


8.	Jupyter has been already preinstalled in the Anaconda environment. We then need to install and enable Widget plugin for AzureML notebooks by following commands

```
conda install ipywidgets 
jupyter nbextension install --py --user azureml.widgets 
jupyter nbextension enable azureml.widgets --user -–py
```

Now you are all set! 
During the workshop, please start your AML environment terminal as shown in ***Step 6***

## In case you have already have Miniconda installed

please create a new environment:
```sh
conda create -n azureml -y Python=3.6 
conda activate azureml
```
Then follow ***Step 7 and 8*** in the above instructions

## Last but not least:

In the workshop, we will run notebooks in https://github.com/Azure/MachineLearningNotebooks. 

Please also be sure to have git installed on your PC from https://git-scm.com/downloads 


