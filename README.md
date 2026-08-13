# Diya
Light illumination device for cells cultured in multiwell plates or culture dishes

## hardware
- CAD files for hardware designs
- More_CAD contains files for Adafruit 64x64 P3 board and a container for the controller
- Assembly instructions

## software
- Source code for Diya GUI
- See Output Folder for Windows Installer
- Diya_Neuron_Installer is Inno Setup file for the creation of the Installer

## Advanced - Modification Descriptions
- Added this to Line 354 - 355 of mainWidget.py while changing subsequent lines:
    - self.StepGBoxes[step_nr][6].setDecimals(2)
    - self.StepGBoxes[step_nr][6].setSingleStep(0.02)
    - self.StepGBoxes[step_nr][6].setSuffix(' sec')
    - self.StepGBoxes[step_nr][6].setMaximum(59.99)
- Line 333 of mainWidget.py changed to:  QSpinBox(), QSpinBox(), QDoubleSpinBox(),
- framerate (limiting factor) on line 47 of setup.py was changed to 1/3000 for 20 ms times
- Line 401 of makegif.py changed from fps=10 to fps=50 (20 ms times)

## Other Notes
- The exported GIFs only make frames every 20 ms, so steps at 0.01, 0.03, 0.05... seconds may not work as intended
- 10 ms frame times do not work with HUIDU technology/ software (hard limit seems to be at 60 FPS, but only 50 FPS was tested)
