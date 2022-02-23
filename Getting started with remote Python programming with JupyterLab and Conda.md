Getting started with remote Python programming with JupyterLab and Conda
=================

The following tutorial will walk you through the preparations you need to make to work with Python on the linux server of our lab using Conda and the JupyterLab IDE.
Let's get started  :hatching_chick:

#### <ins>Connecting to the server: <ins />

Open the terminal and connect to the lab's server with your user through ssh:

```
ssh username@132.68.111.84
```

<img src="misc/images/conda.png" width="40%" height="40%">


Conda is an open-source package management system and environment management system that runs on Windows, macOS, and Linux.

Conda quickly installs, runs, and updates packages and their dependencies. Conda easily creates, saves, loads, and switches between environments on your local computer.

[Click here for further reading about the Conda package manager.](https://docs.conda.io/projects/conda/en/latest/user-guide/tasks/manage-environments.html)

#### <ins>Download and install the python version of miniconda (minimal installer for Conda): <ins />

Create a directory for the miniconda software installation :

```
mkdir miniconda_installation
```

Move to the miniconda installation directory:

```
cd miniconda_installation
```

Run the following line to download the miniconda installation:
```
curl -O "https://repo.anaconda.com/miniconda/Miniconda3-py39_4.10.3-Linux-x86_64.sh"
```

After the download is finished, run the installation:

```
bash Miniconda3-py39_4.10.3-Linux-x86_64.sh
```

Finally, add miniconda path to the server system, so the conda commend would be recognized: 
  
 ```
 export PATH=~/miniconda3/bin:$PATH
 source .bashrc
 ```
Great job! :100: You have the Conda package manager installed. :snake:

Now, let's create our first conda environment.

#### <ins> Creating a Conda environment: <ins/>

A Conda environment is a directory that contains a specific collection of Conda packages that you have installed. It will help you to manage dependencies between packages and isolate projects.

[Click here for further reading about Conda environments](https://docs.conda.io/projects/conda/en/latest/user-guide/concepts/environments.html)

Every time you enter your terminal it will load the Conda "base" environment.
Avoid using the base environment and use proprietary environments to avoid conflicts between your packages over your various projects.

Create a new virtual environment (here the name of your environment is "myenv" and it will use python 3.9):
```
conda create -n myenv python=3.9
```

Activate the new environment by running:
```
conda activate myenv
```

You'll have to activate your the environment you want to use every time you enter the terminal.

To check what Conda environments you have and which is active, run:
```
conda env list
```

<img src="misc/images/jupyterlab.png" width="40%" height="40%">

JupyterLab is an open-source web application primarily designed to provide a user interface based on Jupyter Notebook.

JupyterLab enables users to perform work with documents such as Jupyter notebooks, text editors, and custom components, among others, in a flexible, integrated, and extensible manner.

[Click here for further reading about JupyterLab.](https://jupyterlab.readthedocs.io/en/stable/)

#### <ins> Installing JupiterLab and integrate it with a Conda environment: <ins />

First, let's create a proprietary environment for JupyterLab:

```
conda create -n jupyter_env python=3.9
conda activate jupyter_env
```

Install JupyterLab with conda:
```
conda install -c conda-forge jupyterlab
```

To be able to use our Conda environment through JupyterLab we need to assign the conda environment as a Jupyter kernel.

A Jupyter kernel is a "computational engine" that executes the code contained in a Jupyter notebook document.

Assigning the desired conda environment as a Jupyter kernel:
```
conda install -c anaconda ipykernel
python -m ipykernel install --user --name=myenv
```

Fantastic! :100: Now we have a Jupyterlab server that can use our Conda environment. :full_moon: :snake:

Now it's time for small additional tweaks :smile:

#### <ins> JupyterLab Extensions <ins/>

Fundamentally, JupyterLab is designed as an extensible environment.

JupyterLab extensions can customize or enhance any part of JupyterLab.

Here we will install few packages that I think are useful.


[<ins> JupyterLab Git <ins />](https://github.com/jupyterlab/jupyterlab-git)

A JupyterLab extension for version control using Git

```
conda install -c conda-forge jupyterlab jupyterlab-git
```

[<ins> JupyterLab variableInspector <ins />](https://github.com/lckr/jupyterlab-variableInspector)

Jupyterlab extension that shows currently used variables and their values.

```
pip install lckr-jupyterlab-variableinspector
```

[<ins> JupyterLab LSP <ins />](https://github.com/jupyter-lsp/jupyterlab-lsp)

LSP (Language Server Protocol) is a JupyterLab extension that enables inter-process communication to support multiple languages you may want to use.

Some of LSP features:

- Hover shows a tooltip with function/class signature, module documentation and more.
- Diagnostics—colors for critical errors, warnings, etc.
- Easy jump to definition/use.
- Automatic completion for certain characters when triggered.
- Diagnostic panel.

```
conda install -c conda-forge 'jupyterlab>=3.0.0,<4.0.0a0' jupyterlab-lsp
```
```
pip install 'python-lsp-server[all]'
R -e 'install.packages("languageserver")'
```

Almost finished! Now all we have to do to activate the Jupyter server on our remote host, so it will be accessible from our local environment (your personal computer).

#### <ins> Setting up a remote JupyterLab server <ins />

For this task we will use tmux.

tmux is an open-source terminal multiplexer for Unix-like operating systems. It allows multiple terminal sessions to be accessed simultaneously in a single window. It is useful for running more than one command-line program at the same time.

[Click here for further reading about tmux](https://github.com/tmux/tmux/wiki) <br />
[Click here for a great tmux cheatsheet](https://tmuxcheatsheet.com/)

Start a new session with the name jupyter_server:
```
tmux new -s jupyter_server
```

Activate your jupyter environment:

```
conda activate jupyter_env
```

Configure Jupyter Lab Password:
```
jupyter notebook --generate-config
jupyter notebook password
```

Move to your main working directory and start JupyterLab on the remote server:
(change 1234 to your own unique port, it will be used to access to your server)

```
cd directory_name
jupyter-lab --ip 0.0.0.0 --port 1234 --no-browser
```

Now your server is working, press `ctrl + b + d` to quit the server session.

If you want to make changes on your server or to reset it and so on, you can enter your session by
```
tmux at -t jupyter_server
```

To check what tmux sessions you have and which is active, run:
```
tmux ls
```

Congratulation! you finished setting up your remote host for Python programming with JupyterLab and Conda. Enjoy your good job cookies  :cookie: :cookie: :cookie:

Now you can access your server from your local computer through:
(change 1234 to your port number) <br />
`http://132.68.111.84:1234/lab/`

# <ins> FAQ: <ins />
