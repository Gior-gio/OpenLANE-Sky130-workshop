# OpenLANE-Sky130-workshop
Material for the advanced physical design workshop

# Table of Contents
  - [Day 1 - Inception of open-source EDA, OpenLANE and Sky130 PDK](#1st_Day)
  - [Day 2 - Good floorplan vs bad floorplan and introduction to library cells](#2nd_Day)
  - [Day 3 - Design library cell using Magic Layout and ngspice characterization](#3rd_Day)
  - [Day 4 - Pre-layout timing analysis and importance of good clock tree](#4th_Day)
  - [Day 5 - Final steps for RTL2GDS](#5th_Day)

# 1st_Day
## PDKs and Libraries
First, we look for the PDKs:
<img src="Screenshots/1_PdkCheck.png">

And for the libraries:
<img src="Screenshots/1_LibraryCheck.png">
<img src="Screenshots/1_LibRefCheck.png">

## Docker and OpenLane
We use Openlane with Docker:
<img src="Screenshots/1_DockerOpenLane.png">

Preparing the project _picorv32a_
<img src="Screenshots/1_OpenPicorv32a.png">

Checking reports:
<img src="Screenshots/1_RunOpenLaneCheck.png">
<img src="Screenshots/1_tmpCheck.png">

## Synthesis
Running Synthesis:
<img src="Screenshots/1_RunSynthesis.png">

Checking Synthesis reports:
<img src="Screenshots/1_SynthesisCheck.png">


You can see some statistics related to the design

<img src="Screenshots/1_Picorv32aStatistics.png">
<img src="Screenshots/1_Picorv32aStatisticsCont.png">
<img src="Screenshots/1_PrintingStatistics.png">
For the Flip flop ratio: FFr = 1613/14876 = 10.85%

# 2nd_Day
## Floorplanning in our project 
Checking the variables used in this stage:
<img src="Screenshots/2_VarINFO.png">

floorplan.tcl:
<img src="Screenshots/2_floorplandDOTtcl.png">

config.tcl:
<img src="Screenshots/2_configtcl.png">

Running floorplan:
<img src="Screenshots/2_floorplanEnd.png">

Checking in logs folder:
<img src="Screenshots/2_floorplanLog.png">
<img src="Screenshots/2_ioPlacer.png">

Checking .def file:
<img src="Screenshots/2_ioPlacer.png">

Then, we open Magic:
<img src="Screenshots/2_OpenMAGIC.png">
<img src="Screenshots/2_TryingMagic.png">

## Placement:

We continue with Placement
<img src="Screenshots/2_Placement.png">

And the new layout:
<img src="Screenshots/2_LayoutPlacement.png">
<img src="Screenshots/2_InternalStructureLayout.png">

# 3rd_day

## Clonning git
First, we clone this repository https://github.com/nickson-jose/vsdstdcelldesign.git
<img src="Screenshots/3_ClonningGit.png">


Opening the inverter layout:
<img src="Screenshots/3_InverterLayout.png">


Checking the layout:
<img src="Screenshots/3_CheckLayoutInverter.png">


Generating a DRC error:
<img src="Screenshots/3_LayoutDRCError.png">

## Spice
Extracting to spice:
<img src="Screenshots/3_OriginalSpice.png">

Editing this document:
<img src="Screenshots/3_NewSpice.png">

Running simulation with _nspice_:
<img src="Screenshots/3_SpiceSimulation.png">

Calculating rise, fall and propagation delay:
<img src="Screenshots/3_FallTime.png">
<img src="Screenshots/3_RiseTime.png">
<img src="Screenshots/3_PropagationDelay.png">

trise = 0.1356 ns
tfall = 0.0508 ns
PropDelay = 0.0606 ns

#4th Day
## Export to .lef
We edit and generate a .lef file from the last inverter:
<img src="Screenshots/4_SlightlyEditedLayout.png">
<img src="Screenshots/4_GeneratingLEF.png">
<img src="Screenshots/4_LefFIle.png">

To use them, we have to edit the config.tcl
<img src="Screenshots/4_EditConfigtcl.png">

## Reruning synthesis 
<img src="Screenshots/4_RunningSynthesisaAfter1000attemps.png">
<img src="Screenshots/4_extraoptionsafterSynthesis.png">
<img src="Screenshots/4_NewSynthesis.png">
<img src="Screenshots/4_NewAreaAfterSynthesis.png">

Trying to improve timing:
<img src="Screenshots/4_Morestrategies.png">
