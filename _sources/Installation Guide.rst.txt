.. _Installation Guide:
Installation Guide
==================

Source
------

Our code is based on Python version 3.9 and Pytorch version 1.11.0.
Open-TI provides installation from the source code. 
Please execute the following command to install and configure our environment.

.. code-block:: shell

	clone https://github.com/DaRL-LibSignal/OpenTI.git
	cd OpenTI
	pip install -r requirements.txt
	sudo apt-get install python3-tk

Configuration
-------------

LLM Configuration
^^^^^^^^^^^^^^^^^

First, you need to configure OpenAI-Key. Please create a `./config.yaml` file in the root directory and add the following content to the file (please modify the content to your own settings):

.. code-block:: shell

	OPENAI_API_TYPE: 'openai' #'azure'  OR 'openai'
	# for 'openai'
	OPENAI_KEY: '' # your openai key


Here we recommend using ChatGPT-3.5 to run as LLM. If you want to use your own LLM, please refer to `LangChain-Large Language Models <https://python.langchain.com/docs/modules/model_io/models/>`_ to define Your own LLM. In this case, please modify the following sections in `./DataProcessBot.py` and `./SimulationProcessBot.py` to configure your own LLM.


Simulator environment configuration
-----------------------------------

Though CityFlow, SUMO,  and LibSignal are stable under Windows and Linux systems, we still recommend users work under the Linux system.

CityFlow Environment
^^^^^^^^^^^^^^^^^^^^

To install CityFlow simulator, please follow the instructions on `CityFlow Doc <https://cityflow.readthedocs.io/en/latest/install.html#>`_

.. code-block:: shell

	sudo apt update && sudo apt install -y build-essential cmake
	git clone https://github.com/cityflow-project/CityFlow.git
	cd CityFlow
	pip install .

To test configuration:
.. code-block:: shell

	python3
	import cityflow
	env = cityflow.Engine

SUMO Environment
^^^^^^^^^^^^^^^^

To install SUMO environment, please follow the instructions on `SUMO Doc <https://epics-sumo.sourceforge.io/sumo-install.html#>`_`

.. code-block:: shell

	sudo apt-get install cmake python3 g++ libxerces-c-dev libfox-1.6-dev libgdal-dev libproj-dev libgl2ps-dev swig
	git clone --recursive https://github.com/eclipse/sumo
	export SUMO_HOME="$PWD/sumo"
	mkdir sumo/build/cmake-build && cd sumo/build/cmake-build
	cmake ../..
	make -j$(nproc)

If you cannot make the directory sumo/build/cmake-build, you could try the command below

.. code-block:: shell

	cd sumo
	mkdir build
	cd build
	mkdir cmake-build
	cd cmake-build

To test installation:

.. code-block:: shell

	cd ~/sumo/bin
	./sumo


To add SUMO and traci model into the system PATH, execute the code below:

.. code-block:: shell

	export SUMO_HOME=~/sumo
	export PYTHONPATH="$SUMO_HOME/tools:$PYTHONPATH"

To test configuration:

.. code-block:: shell

	python3
	import libsumo
	import traci


LibSignal Environment
^^^^^^^^^^^^^^^^^^^^^

To install LibSignal environment, please follow the instructions

.. code-block:: shell

	cd LibSignal
	pip install -r requirements.txt
	pip3 install torch torchvision torchaudio --extra-index-url https://download.pytorch.org/whl/cu113
	pip install cmake
	pip install lmdb


Start Running
-------------

If you install all the requirments below, you can run Open-TI now.

.. code-block:: shell

	cd OpenTI
	cd pivotalAgent
	python3 executor.py


