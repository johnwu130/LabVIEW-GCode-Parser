# LabVIEW-GCode-Parser
This SubVI resolves GCodes commands into an array of clusters.  The command array can then be used in other loops to issue commands to the motion controller.  

Some GCode background:

This is the standard format for most GCode commands:

  G1 Z-0.2432 F127.0
  
  G1 F127.0
  
  G1 X23.4002 Y26.2105 Z-0.1604
  
  G1 X23.4153 Y25.2337 Z-0.1307
  
  G1 X23.3739 Y24.1009 Z-0.1732
  
  
There should be spaces between the parameters and the initial GCode.
Also, this is inherently modal. For instance F127.0 will stay with the last 3 commands.
Not all Gcode will follow this format, but please report any bugs to make this code more robust.
For more on GCode, visit here: http://en.wikipedia.org/wiki/G-code.

Features:

1. Robust parsing ability to deal lack of spaces or formatting characters.
2. Fast! Can parse 100000+ commands in less than a second.

Instructions for use:

1. Open the LV Project "GCode Parser - SoftMotion Example.lvproj"
2. Run "GCode Parser - SoftMotion Example.vi"
3. Select a sample GCode from the dialog window.  Watch run.

Notes:

In the SoftMotion example, only the following GCodes are supported:
G0 - Rapid Positioning
G1 - Linear Interpolation
G92 - Reset Position

G2, G3 Arc moves are not supported in the example right now, but it wouldn't be hard to add.
This example is intended for someone to modify and combine with the motion driver of their choice.
For ex: NI SoftMotion, FlexMotion, motion VIs from other vendors, etc.
