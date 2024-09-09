**WINDOWS SAGE AND VSCODE INSTALL INSTRUCTIONS**

### 1. Install Windows Linux Ubuntu
Click on the windows search bar and search "Turn Windows features on or off"
Find a check box for "Windows Subsystem for Linux" and make sure its checked. Restart your PC.
Open a command prompt as an administrator and type 
```bash
wsl --install
```

You will need to restart during the process if it asks.
Complete the linux setup process, any username / password
Close the terminal.


### 2. Run the following commands. These may take a few minutes
```bash
sudo apt update
sudo apt install sagemath 
sudo apt install python3-pip
sudo apt upgrade
```

Next set of commands. Make sure you click Enter or type `yes`or  `y` when it asks:
```bash
curl -L -O "https://github.com/conda-forge/miniforge/releases/latest/download/Miniforge3-$(uname)-$(uname -m).sh"
bash Miniforge3-$(uname)-$(uname -m).sh
conda create -n sage sage python=3.11
conda activate sage
```
If for whatever reason it says 'conda is not a valid command', try re-installing:
```bash
curl -L -O "https://github.com/conda-forge/miniforge/releases/latest/download/Miniforge3-$(uname)-$(uname -m).sh"
bash Miniforge3-$(uname)-$(uname -m).sh -u
conda create -n sage sage python=3.11
conda activate sage
```

### 3. To activate sage, type the following commands into a new Ubuntu terminal.
```bash
sage
```
Sage is now running!
You try doing 
`2^3` and pressing Shift-Enter 
Whenever you need to run sage, open an Ubuntu terminal and run the command:
```bash
sage
```
Whenever you need to quit sage, type `quit` or close the terminal.
Remember this ubuntu terminal runs linux so all linux commands apply here like `ls` and `cd`.
However, this format is not particularly useful. 

### 4. VS Code support
Open an ubuntu terminal and enter:
```bash
code .
```

This will open VS code in the home directory.
(If there is a popup in the bottom right of recommended plugins to install, install them).
Next install the 'Jupyter' VSCode extension (from Microsoft) (Google how to instal VSCode extensions if you don't know how).
Install the 'WSL' VS Code extension (from Microsoft).
Close VSCode and the terminal and reopen both.
Then create a new Jupyter Notebook: Ctrl-Shift-P type "Create: New Jupyter Notebook" and click enter.
Lastly we need to set the kernel. 
In the top right corner of the VS Code workspace, click select Kernel ->Jupyter Kernel -> SageMath 9.5

To test it, run the following sage code:
```py
u, v = var('u,v')
f1 = (4+(3+cos(v))*sin(u), 4+(3+cos(v))*cos(u), 4+sin(v))
f2 = (8+(3+cos(v))*cos(u), 3+sin(v), 4+(3+cos(v))*sin(u))
p1 = parametric_plot3d(f1, (u,0,2*pi), (v,0,2*pi), texture="red")
p2 = parametric_plot3d(f2, (u,0,2*pi), (v,0,2*pi), texture="blue")
p1+p2
```
You should see a red and blue donut.

### How to reopen and use sage.
In Windows open an Ubuntu terminal.
Enter `code .`

**Create a new File:**
Create a new Jupyter Notebook: Ctrl-Shift-P type "Create: New Jupyter Notebook" and click enter.
Select Kernel -> SageMath 9.5.

**Open / Close Old Files:**
To save, do Ctrl-S then click `ShowLocal`and save it on your computer. Opening a file do Ctrl-O -> `ShowLocal` and select the file you wish to use. 
You need to open VScode through Ubuntu then open the file, just double clicking the file in Windows file explorer will not work.



More Info:
https://doc.sagemath.org/html/en/installation/index.html
https://doc.sagemath.org/html/en/installation/launching.html#sec-launching
