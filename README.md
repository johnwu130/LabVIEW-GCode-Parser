# LabVIEW-GCode-Parser
A SubVI that parses GCode commands.

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

Features:

1. Robust parsing ability to deal lack of spaces or formatting characters.
2. Fast! Can parse 100000+ commands in less than a second.

