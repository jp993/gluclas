# GLUCLAS 

<a rel="license" href="http://creativecommons.org/licenses/by-nc-nd/4.0/"><img alt="Licenza Creative Commons" style="border-width:0" src="https://i.creativecommons.org/l/by-nc-nd/4.0/88x31.png" /></a>

<b>Gluclas</b> (GLUcose CLamp ASsistant) is a free software for suggesting glucose infusion rate adjustments during manual glucose clamp experiments. 

<p align="center">
  <img src="https://user-images.githubusercontent.com/50666703/145588697-8f8cb6cc-f28e-425e-8d3f-a136fdd52046.png"/>

## Disclaimer
<b>Gluclas</b> is not an approved medical software nor a medical device. It should be considered as an investigational tool aimed at providing infusion rate suggestions that must be critically interpreted, reviewed, and verified by the clinician in charge of conducting the experiment, who remains the ultimate responsible for clinical decisions. The authors of this software decline any responsibility for medical consequences of inadequate suggestions.

## Requirements
<b>Gluclas</b> is developed in MATLAB®, but no license is required to run the software. All <b>Gluclas</b> requires is the MATLAB® Runtime (v. 9.11 or higher) to be installed in your computer. 

You can download the appropriate version of the MATLAB® Runtime for your OS [here](https://it.mathworks.com/products/compiler/matlab-runtime.html).

## Software description
The two main components of <b>Gluclas</b> are a proportional-integral-derivative (PID) control algorithm, which is used to compute GIR suggestions, and a Graphic User Interface (GUI) for data recording, visualization, and correction. An extensive description of the control algorithm can be found in [here](https://www.sciencedirect.com/science/article/pii/S0169260722004850?via%3Dihub). The GUI is minimalistic, and the computation cost of the control algorithm is negligible – which reduces the hardware requisites for running the software. 
  
### Starting and protocol settings
When starting a new experiment, a “Settings” window requests information about the subject and the protocol of the experiment. The “Patient data” section collects patients characteristics. The “Type of clamp” section allows to choose between one of three different GC types: “Hypoglycemic”, “Euglycemic” and “Hyperglycemic”. To help the user, the fields in the “Protocol settings” section are pre-filled with default settings based on the type of clamp and patient’s information. 
  
Depending on the type of GC, different reference signals are proposed: a constant reference of 12.4 mmol/l for the “Hyperglycemic”, a constant reference of 5.5 mmol/l for the “Euglycemic” or a time-varying reference that slowly reaches 2.5 mmol/l for the “Hypoglycemic”. In the “Euglycemic” and “Hypoglycemic” clamp, the “Insulin solution infusion rate” is precompiled to suggest an infusion rate of 40 mU/ m2/min per body surface area (m2). Body surface area (BSA) is computed using the Du Bois formula. These pre-defined values are commonly used in literature and can be over-written by the user to fully customize the protocol. 
  
The “Advanced settings” button opens a new window where the user can specify the desired measurement units for BG concentration (“mmol/l” or “mg/dl”). In GC experiments, glucose and insulin are infused using volumetric pumps. For this reason, the “Advance settings” windows allow the user to specify the concentration of glucose and insulin in the solutions. Glucose concentration will later be used to suggest GIR adjustments in ml/h. 
  
### Reading and control
Once patient’s data are provided and experimental settings are defined, the user can access to the “Experiment” window. The time of acquisition of all the measurements is provided and recorded as the number of minutes passed since the start of the experiment. Users can set the beginning of this timer by clicking on the “Calibrate time” button. By clicking on “Start Reading”, the software will enter the “Reading mode”, which consists exclusively in monitoring and recording subjects’ BG levels. In this mode, a pop-up window will appear every 5 minutes to ask the investigator for a BG measurement. If no measurement is provided within 5 minutes, the pop-up window will automatically close. 
  
When the button “Control to reference” is clicked, the experiment enters in the “Control mode”. From this moment, the pop-up window will also return a suggested GIR, as shown in Figure 6. If the investigator decides to use a different GIR from the one suggested by the controller, then the correct GIR should be reported here in the field “Actual GIR”. This pop-up window will also appear every 5 minutes for nudging the users to comply with the sampling period. 
  
Lastly, when the button “Restore euglycemia” is clicked, the reference signal will be over-written with 4.5 mmol/l. This mode can be particularly useful to bring patient’s BG to a physiological concentration after the completion of the experiment in the case of hypoglycemic clamp experiments.  
 
It is possible to record additional signals during the experiment (e.g., insulin, glucose intake, additional BG measurements). It is also possible to correct any inserted measurement. A backup file is updated at the end of any BG measurement to restore the experiment in case of unexpected interruptions of the program. 
  
At the end of the experiment, data can be saved automatically in both .mat and .xlsx format. 


## Distribution

<p xmlns:cc="http://creativecommons.org/ns#" xmlns:dct="http://purl.org/dc/terms/"><span property="dct:title"><b>Gluclas</b></span> is licensed under <a href="http://creativecommons.org/licenses/by-nc-nd/4.0/?ref=chooser-v1" target="_blank" rel="license noopener noreferrer" style="display:inline-block;">Attribution-NonCommercial-NoDerivatives 4.0 International  <img style="height:22px!important;margin-left:3px;vertical-align:text-bottom;" src="https://mirrors.creativecommons.org/presskit/icons/cc.svg?ref=chooser-v1"><img style="height:22px!important;margin-left:3px;vertical-align:text-bottom;" src="https://mirrors.creativecommons.org/presskit/icons/by.svg?ref=chooser-v1"><img style="height:22px!important;margin-left:3px;vertical-align:text-bottom;" src="https://mirrors.creativecommons.org/presskit/icons/nc.svg?ref=chooser-v1"><img style="height:22px!important;margin-left:3px;vertical-align:text-bottom;" src="https://mirrors.creativecommons.org/presskit/icons/nd.svg?ref=chooser-v1"></a></p>
