# vicuna-installation-guide-on-mac
The "vicuna-installation-guide-on-mac" provides step-by-step instructions for installing Vicuna-7B on Mac
## Requirements
- You need to have macOS Ventura 13.3 or newer
- You need to install Homebrew
```
/bin/bash -c "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/HEAD/install.sh)"
```
- You need to install git
```
brew install git
```
- Make sure you are using Python 3.10
```
brew install python@3.10
```
## Install text-generation-webui
### Clone the repository
```
git clone https://github.com/oobabooga/text-generation-webui.git
```
Enter the webui’s folder by running
```
cd text-generation-webuiCopied!
```
### Create and activate a virtual environment
Make sure you are using Python 3.10.
```
python3 --version
```
You should see you are running Python 3.10.x

Now creates a virtual environment to get a clean slate of Python environment.
```
python3 -m venv venv
```
Activate the virtual environment.
```
source venv/bin/activate
```
You should see the label (venv) in front of your prompt.
### Install the required packages
Run the following command to install the required packages.
```
pip install -r requirements.txt
```
The released Pytorch package won’t work for text-generation-webui on Mac. You need to install the nightly development build.
```
pip install -U --pre torch torchvision -f https://download.pytorch.org/whl/nightly/cpu/torch_nightly.html
```
## Vicuna model
### Download the model
```
python download-model.py chharlesonfire/ggml-vicuna-7b-4bit
```
### Running the model
```
python server.py --chat --threads 4
```
### Using the webui
Go to the URL http://127.0.0.1:7860 in your browser to start the webui.
Navigate to the Model page. Select the 7B model.
Chat with Vicuna on the text generation page.
