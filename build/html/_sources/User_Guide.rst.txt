.. _User_Guide:
User Guide
==========

Here are several questions and answers that we will asked for and replied by Open-TI.

Fuzzy Understand
----------------

Bilingual Support
-----------------

Detailed Embodiment
-------------------

introduceYourself
^^^^^^^^^^^^^^^^^

introduceYourself can help people know what's Open-TI and how can it do.

* Tell me about yourself.

queryAreaRange
^^^^^^^^^^^^^^

queryAreaRange can help you obtain area information, specifically the longitudes and latitudes of a point of interest on the map.

* Where's Arizona State University?

showOnMap
^^^^^^^^^

showOnMap is used to query and show the map of the interested place.

* Can you show me the map of Arizona State University?

autoDownloadOpenStreetMapFile
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

autoDownloadOpenStreetMapFile automatically downloads map data from OpenStreetMap for a specified area.

* Can you download the OSM file of Arizona State University?

networkFilter
^^^^^^^^^^^^^

networkFilter filters the road network based on required categories, return the file
path of a filtered road network that emphasizes lanes of interest.

* I am wondering bikable lanes in the place, can you show me that information?
* I am wondering the railway lanes in this place, can you show me the information?
* How about walkable area?

simulateOnSumo
^^^^^^^^^^^^^^

simulateOnSumo are commonly integrated by different implementations.

* Help me to run simulation on SUMO in this area.

simulateOnLibsignal
^^^^^^^^^^^^^^^^^^^

simulateOnLibsignal applies multiple algorithms to control traffic signal control while the Webster method is used in TrafficGPT.

* Can you run the simulator on Libsignal using CityFlow environment, DQN policy, and episode 15?
Please note that you can replace Cityflow with SUMO.
You can replace DQN with frap, presslight, mplight, fixedtime,or sotl.
You can revise how many episodes do you want to run (it will default as 5).

generateDemand
^^^^^^^^^^^^^^

GenerateDemand generates demand based on OpenStreetMap data.

* Please generate the demand file using the OSM file of Arizona State University.

simulateOnDLSim
^^^^^^^^^^^^^^^

simulateOnDLSim simulates on the DLSim multi-resolution traffic simulator.

* Please execute the simulator DLSim platform using the generated demand files at path ./Data/demand/arizona_state_universty.

logAnalyzer
^^^^^^^^^^^

logAnalyzer is designed to interpret and help the user understand the log and config files, similar to retrieving data from .XML files in TrafficGPT.

* Hi this is the path of log file ./LibSignal/configs/tsc/colight.yml can you help me to understand and interpret it?
* In the same file, there are more parameters in each catagories, for example, in model, there are "graphic": True, vehicle_max: 1, learning rate: 0.001, batch_size: 64, gamma: 0.95, epsilon: 0.8, epsilon_decay: 0.9995, epsilon_min: 0.01, grad_clip: 5.0. Please help me understand in details.

resultExplainer
^^^^^^^^^^^^^^^

resultExplainer can interpret results to provide insights.

* Please run simulation on Libsignal using CityFlow, algorthm fixedtime, and episode 5.
* Please run simulation on Libsignal using CityFlow, algorthm DQN, and episode 5.
* Can you analyze the log file of running LibSignal on simulator CityFlow, algorthm DQN, and episode 5 and compare with on simulator CityFlow, algorthm fixedtime, and episode 5?

demandOptimizer
^^^^^^^^^^^^^^^

demandOptimizer approximates the origin-destination demand to fit realistic observation.

* Hi I have provided the O-D demand zone information in file "pure _simulate/taz.add.xml", Can you show me the zone visualization based on original map data: "map.net.xml"?
* I have the real-world observation data collected in file “pure_simulate/obs.csv”, in this sumo map, the observation point are: lane="1089324756#1_1" pos="10.10” lane="1089324756#1_0" pos="10.53" Please set detectors here following the info in “pure_simulate/monitor.add.xml” 
* Please run the demand optimization by follow the process in file using the Genetic Algorithm : “pure_simulate/optimize_od.py” and visualize the comparison result to observation data.

