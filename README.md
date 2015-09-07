# Text Messaging Telemetry for DroneKit
Control Rovers, Copters, or Planes via inexpensive text messaging from within DroneKit

Dependencies:  

    -- sudo pip install python-gsmmodem
    
    -- sudo pip install pymavlink
    
    -- sudo pip install pylzma
    
    -- sudo pip install mavproxy
    
    -- sudo pip install droneapi


How to launch text messaging telemetry between your APM Rover and Ground Station computer:

    --Copy project files to your vehicle's companion computer (e.g. Raspberry Pi) and your laptop.
    
    --On your ground station computer enter the following command:  
    
        python LaunchTelemetry.py -ground
        
    --On the vehicle's companion computer, launch the script from Mavproxy/DroneKit:
    
        navigate to the directory where LaunchTelemetry and TextMessageTelemetryClass are located
        
        sudo mavproxy --master=/dev/ACM0 --baudrate=115200  (this is for an APM/Pixhawk connected via USB. Use /dev/AMA0 when using a serial cable)
        
        (inside mavproxy, enter the following) module load droneapi.module.api
        
        (inside mavproxy, enter the following) api start LaunchTelemetry.py  
        

Supported Hardware/Software Configuration:

    * Ground Station
        * Mac laptop/desktop
        * APM Planner 2 software
        * Sierra 313u (AT&T 313u) GSM modem
        * AT&T's $2/day pay-as-you-go unlimited texting plan
    
    * Vehicle
        * Raspberry Pi "companion computer" connected to autopilot via serial or USB cable
        * APM 2.6 or Pixhawk autopilot
        * Sierra 313u (AT&T 313u) GSM modem
        * AT&T's $2/day pay-as-you-go unlimited texting plan


Changelog: 

    -- 5 Sep 2015 -- Under Development 
    
License information:

    -- Copyright (C) 2015 Chambana

    -- License: GNU Lesser General Public License, version 3 or later; see COPYING included in this archive for details.