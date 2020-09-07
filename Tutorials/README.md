#  Jupyter* Notebook Tutorials for using the Intel® Distribution of OpenVINO™ toolkit

## Introduction

Jupyter* Notebook tutorials are provided to demonstrate step-by-step how to use the Intel® Distribution of OpenVINO™ toolkit.  Outlines for each tutorial:

- [Image Classification Tutorial](./classification/tutorial_classification_sample.ipynb)	(See the completed tutorial with output [here](./classification/tutorial_classification_sample_completed.ipynb))
	- Prerequisites
	- Introduction
		- Key concepts
			- Intel® distribution of OpenVINO™ toolkit overview and terminology
		- Input preprocessing
		- Batch size
			- Batch size and its effects on input and output data is model dependent
			- How batch size is set
		- Performance counters
	- Sample application
		- Imports
		- Configuration
		- Create inference engine instance
		- Read network
		- Load model
		- Load labels
		- Prepare input
		- Run inference
		- Process and display results
	- Exercise #1: Run a different image
	- Exercise #2: (Optional) Run your own image
	- Inferring input images in batches
		- Preparing a batch of inputs
		- Running inference on a batch of inputs
		- Processing and displaying a batch of outputs
	- Exercise #3: (Optional) Run your own batch of images
	- Report performance counters
	- Cleanup
	
- [Object Detection Tutorial](./object_detection/tutorial_object_detection_ssd.ipynb)	(See the completed tutorial with output [here](./object_detection/tutorial_object_detection_ssd_completed.ipynb))
	- Prerequisites
	- Introduction
		- Key concepts
			- Intel® distribution of OpenVINO™ toolkit overview and terminology
		- Input preprocessing
	- Sample application
		- Imports
		- Configuration
		- Create inference engine instance
		- Read network
		- Load model
		- Load labels
		- Prepare input
		- Run inference
		- Process results
		- Display results
	- Exercise #1: Run a different image
	- Exercise #2: (Optional) Run your own image
	- Exercise #3: Running inference on video
	- Exercise #4: (Optional) Run your own video
	- Cleanup


- [Style Transfer Tutorial](./style_transfer/tutorial_style_transfer_sample.ipynb)	(See the completed tutorial with output [here](./style_transfer/tutorial_style_transfer_sample_completed.ipynb))
	- Prerequisites
	- Introduction
		- Key concepts
			- Intel® distribution of OpenVINO™ toolkit overview and terminology
		- Input preprocessing
	- Sample application
		- Imports
		- Configuration
		- Create inference engine instance
		- Read network
		- Load model
		- Prepare input
		- Run inference
		- Process and display results
	- Exercise #1: Run a different image
	- Exercise #2: (Optional) Run your own image
	- Exercise #3: Running inference on video
	- Exercise #4: (Optional) Run your own video
	- Cleanup

## Prerequisites 
### Hardware
The tutorials are configured to run on the same host CPU that JupyterLab\* is run on.  The host system and CPU must meet the [system requriements for the Intel® Distribution of OpenVINO™ toolkit](https://software.intel.com/content/www/us/en/develop/tools/openvino-toolkit/system-requirements.html).


### Software
The following sections cover the software that is required to be installed before running the Jupyter* Notebook tutorials locally on your system.
#### [Intel® Distribution of OpenVINO™ toolkit](https://software.intel.com/openvino-toolkit)

To run the tutorials, the Intel® Distribution of OpenVINO™ toolkit and its dependencies must already be installed and verified using the included demos.   The following links may be used to determine system requirements and to begin installation:

- [System Requirements](https://software.intel.com/content/www/us/en/develop/tools/openvino-toolkit/system-requirements.html)
- [Linux Installation Instructions](https://software.intel.com/en-us/articles/OpenVINO-Install-Linux)

#### [JupyterLab*](https://jupyter.org/)

- Please follow the provided [installation instructions](https://jupyter.org/install.html) to install JupyterLab\*.  The following command substitutions may be necessary to ensure that Python* v3.5 (or higher) is used:
   - For `conda [...]`, use: `conda python=<3.x> [...]`
      - Run `python3 --version` to see what version that is installed and replace "<3.x>" above with the first two version numbers reported (Example: for "Python 3.6.12", use "python=3.6")
   - For `pip [...]`: `pip3 [...]` or `python3 -m pip [...]`

**Note**: It is recommended that JupyterLab* be installed into directories owned by the user (e.g. the user's home directory using `conda` or  using `pip` with `install --user`) and not installed into system directories that require root permissions.  This will allow the user to more easily make modifications to the JupyterLab* configuration such as installing extensions using the JupyterLab* Extension Manager.

#### [Git](https://git-scm.com/)

The `git` utility or equivalent must be already installed to download the tutorials from the GitHub repository.

### Internet connection

Please ensure that your development platform is connected to a network and has Internet access. To download all the tutorial files, you will need to access GitHub on the Internet.

## How to run the Jupyter* Notebook tutorials

The next sections will step you through downloading and then running the Jupyter* Notebook tutorials.

### Downloading the tutorials from the GitHub repository

The first thing we need to do is create a place for the Jupyter* Notebook tutorials and then download them.  To do this, we will create a directory called `jnb_tutorials` and use it to store the files that downloaded from the GitHub repository using the `git` command.  Follow these steps to get started:

1. Bring up a command shell prompt by opening a terminal (such as xterm) or selecting a terminal that is already open.
2. Create a `jnb_tutorials` directory for downloading the tutorials and then change to it:
	```bash
	mkdir ~/jnb_tutorials
	cd ~/jnb_tutorials
	```
3. Clone the repository:
	```bash
	git clone https://github.com/trexdog/openvino-jupyternotebook-tutorials.git
	```
4. Change to the top of the git repository and check out correct version:
	```bash
	cd Tutorials
	git checkout openvino_toolkit_2020_4
	```

### Launch JupyterLab*

After the tutorials are downloaded, JupyterLab* may be started to run the Jupyter* Notebook tutorials.  Follow these steps to start JupyterLab*:

1. Bring up a command shell prompt by opening a terminal (such as xterm) or selecting a terminal that is already open.

2. Change to the `jnb_tutorials` directory, this will become the top directory view within JupyterLab*:

   ```bash
   cd ~/jnb_tutorials
   ```
   
3. Ensure the command line is setup to use the Intel® Distribution of OpenVINO™ toolkit executables and libraries by source-ing the necessary setup script:
   ```bash
   source /opt/intel/openvino/bin/setupvars.sh
   ```
   
4. Start JupyterLab*:
   ```bash
   jupyter-lab
   ```
   JupyterLab* will attempt to start a browser window for you that will be connected to the Jupyter* server.  If the browser cannot be started for any reason, the text output from running `jupyter-lab` will display multiple URLs that you may use to connect a browser to the Jupyter* server.
   
   **Note**: To later stop JupyterLab*, use `Ctrl+C` and answer "y" when you see the prompt "Shutdown this notebook server (y/[n])?".

### Start a Jupyter* Notebook tutorial

From within you browser running JupyterLab*, use the File Browser to select the Jupyter\*  Notebook file for the tutorial that you want to run:

- [Image Classification tutorial](./classification/tutorial_classification_sample.ipynb):
   - **Tutorials/classification/tutorial_classification_sample.ipynb**
- [Object Detection tutorial](./object_detection/tutorial_object_detection_ssd.ipynb):
   - **Tutorials/object_detection/tutorial_object_detection_ssd.ipynb**
- [Style Transfer tutorial](./style_transfer/tutorial_style_transfer_sample.ipynb):
   - **Tutorials/style_transfer/tutorial_style_transfer_sample.ipynb**

#### Optional step: Enable the Table of Contents extension for JupyterLab* 

The [Table of Contents extension for JupyterLab*](https://github.com/jupyterlab/jupyterlab-toc) automatically creates a table of contents for Jupyter* Notebooks, Markdown files, etc. which can be more convenient to navigate the provided tutorials and *README.md* files.  The extension may be installed using either of the following methods:

   **Note**: To install and run JupyterLab* extensions, you may need to install `Node.js` and `npm` which may be done following the [NodeSource* installation instructions](https://github.com/nodesource/distributions/blob/master/README.md#debinstall).

1. Follow the instructions on the [Table of Contents extension for JupyterLab* site](https://github.com/jupyterlab/jupyterlab-toc)   OR
2. Install from within JupyterLab* following these steps:
   1. Enable the Extension Manager by selecting Settings->”Enable Extension Manager”
      1. After selecting it, a pop-up window will appear asking you to approve extensions with a warning that extensions are potentially pose security risks.
   2. The Extension Manager will appear on the left edge at the bottom as a "puzzle piece" icon.  Click the icon.  
      1. A pop-up window may appear asking you to approve extensions with a warning that extensions are potentially pose security risks.
   3. In the Extension Manager on the left, expand the "DISCOVER" section.
   4. Look for the extension "@jupyterlab/toc,  Table of Contents extension for JupyterLab" and click "install" that appears below it and follow any instructions that appear.
   

## Tested environment

The tutorials were tested using the following:

- OS: Ubuntu 18.04 LTS
- JupyterLab: Version 2.2.6
- Intel® Distribution of OpenVINO™ toolkit: Release 2020.4
- Hardware: Intel® i7-7700 CPU