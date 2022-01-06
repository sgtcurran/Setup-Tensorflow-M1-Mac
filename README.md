# Setup-Tensorflow-M1-Mac
How to setup M1 (Metal) Mac - Tendorflow 
# Spent a couple of hours figuring out what need to be installed and in what order to run TensorFlow on a new M1 Mac Mini. I hope this guide will help you and greatly reduce the time required for your initial setup :)

# Step One - Download homebrew via Mac Terminal (copy & Paste) 
/bin/bash -c "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/HEAD/install.sh)"
# Do not forget to configure your shell environment. The Homebrew Path in shell is not default (/opt/homebrew). You will see at the end of the installation instructions to do so. It will be copy and paste two lines of code. It is recommended to close shell terminal and restart before continueing.   
# Step Two - Install xcode select command-line utilities (copy & paste)
xcode-select --install
# Step Three - Using Homebrew to install Miniforge (copy & Paste)
brew install miniforge
# Step Four - Initiate conda base environment (copy & paste)
conda init zsh 
# This will set the python Path to the Miniforge base in your profile. 
# To verify that you have the correct path to Python (copy & paste)
which python
# The command responce should be simular to:
/opt/homebrew/Caskroom/miniforge/base/bin/python
/usr/local/Caskroom/miniforge/base
/opt/homebrew/Caskroom/miniforge/base
# If there is an issue of incorrect paths read https://github.com/conda-forge/miniforge/issues/127 it will help you troubleshoot the issue.
# Step Five - Install Jupyter (copy & paste)
conda install -y jupyter
# Step Six deactivate the base environment (copy & paste)
conda deactivate
# Step Seven - active new virtual environment using conda. "mpl" can be change to anything you want it (copy & past)  
conda create -n mlp 
conda activate mpl
# Step Eight - add Jupyter support to your new enviroment (copy & paste)
conda install nb_conda
# Step Nine - Register your tensorflow environment (copy & paste)
python -m ipykernel install --user --name tensorflow --display-name "Python 3.8 (tensorflow)"
# Step Ten - Install sklean to environment (Copy & Paste)
pip install -U scikit-learn
# Step Eleven -  Install TendorFlow pip package dependencies to environment(Copy & paste)
pip install pip numpy wheel
pip install keras_preprocessing --no-deps
# Step Twelve - Install TensorFlow dependencies (copy & paste)
conda install -c apple tensorflow-deps
# Step Thirteen - Install base TendorFlow (copy & paste)
python -m pip install tensorflow-macos
# Step Fourteen - Install Tensorflow-metal plugin (copy & paste)
python -m pip install tensorflow-metal
# Step fithteen - Install conda pandas 
conda install pandas 
# Step Fithteen - Start Juypter Notebook
jupyter notebook 

