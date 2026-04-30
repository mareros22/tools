layout: page
title: "ModelSim"
permalink: /modelsim
## Getting Started
There are several ways to launch ModelSim. Some courses provide you with a special file that you can store in your project folder, which is used to launch the application within the context of your project.
Here's an alternative to using the LaunchModelSim file:
1. Open the ModelSim application by using a desktop shortcut or searching for the application on your machine
2. Switch to your project directory by using the toolbar at the top of the screen: File>Change Directory...
3. Navigate to your project directory in the pop-up window and click 'OK'

## Running a Testbench
### With a runlab.do file
  1. Find the Transcript window. If you can't find it, click View in the toolbar and select Transcript. 
  2. Enter into the Transcript window `do <filename>`, where `filename` is the name of your runlab file
### Without a runlab.do file
  1. Find the Library window. If you can't find it, click View in the toolbar and select Library.
  2. Expand the "work" dropdown
     <img width="223" height="200" alt="image" src="https://github.com/user-attachments/assets/5662059a-511e-4295-acf7-b9ce9bacc409" />
  3. Double-click the testbench that you want to run
### With Libraries
1. Click Simulate>Start Simulation
2. Click the Libraries tab
3. Add libraries to the Search Libraries First window
4. Return to the Design tab
5. Find the testbench in the Work dropdown and select it as the Design Unit
6. Click OK

## Setting up the Waveforms
If you can't find your waveform window, click View in the toolbar and select Wave. Sometimes it will open in a new window.
### Using a Waveform Format File
If you have a waveform format file, you can include it in your runlab file and the wave output will be formatted automatically. To set up this file, you should follow the instructions for setting up your waveforms without a format file, and then use `Ctrl+S` to save your format file.

### Without a Format File
1. Add signals to the Wave (there are a few options for this)
   - Find signals in the Objects window and drag them into the Wave pane
   - Select signals in the Objects window and right-click, then click Add Wave
   - To add internal signals, expand the dut module in the sim window and click on the submodule to view its signals in the Objects pane
2. Rename signals
   - Click the shell symbol at the bottom of the wave window to toggle between the path names and the signal names <img width="103" height="141" alt="image" src="https://github.com/user-attachments/assets/7e93943a-6a74-46b6-964b-a92f8284064b" />
   - Alt: Double-click signal name to open the Wave Properties window and set the Display name
3. Set radix
   - Right-click signal name in the wave panel and use the Radix drop-down to select the radix
   - Alt: Double-click signal name to open Wave Properties window and use the Radix dropdown in Radix Settings
4. If desired, group signals by selecting their names and right clicking, then click Group...
5. If desired, set signal color by double-clicking the signal name to open the Wave Properties window, then set the Wave Color under Color Settings
6. Once format is configured as desired, if creating a Format file, use `Ctrl+S` to save
7. To re-run the simulation with the new format, find the Simulate tab in the ModelSim toolbar and click Simulate>Run>Run -All
   <img width="265" height="136" alt="image" src="https://github.com/user-attachments/assets/a273d6b9-85e8-4622-a2eb-de55f6dd47e8" />

## Useful Tools
- Press 'C' to zoom in on the active cursor (yellow line)
- Press 'I' to zoom in and 'O' to zoom out
