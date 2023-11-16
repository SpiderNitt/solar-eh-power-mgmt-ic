# solar-eh-power-mgmt-ic
This project aims to create the schematic and layout files (and perform simulation) of a power management IC for solar energy harvesting applications.  

## Environment:  

### Overview:  
1. Cadence Virtuoso is used for the analog design and simulation.
2. Red Hat Linux Enterprise (RHEL) is the OS used.

### Working Directory
1. Make sure your working directory is `/home/work/solar_eh_pmic/`, before typing `virtuoso` in terminal. This is the Virtuoso working directory, where libraries are present, and library references are stored.
2. To change simulation directory (for ADE L), in Virtuoso go to `Tools>ADE L>Setup>Simulator/Directory/Host`. Here, under `Change project directory`, enter `/home/work/solar_eh_pmic/simulation/SIM_IC61`.  

### Directory & File Structure:
1. `adel_config` - Stores simulation configuration files of Spectre (ADE L) simulator, like simulation states, definition files, parametric analysis, expression editor files.
2. `libs` - All libraries are stored here, including gpdk_90. The cds.lib file will index (refer to) the libraries here by their relative paths.
3. `simulation` (gitignored) - Stores simulation results.
4. `specs` - Stores various design specifications and descriptions, purely for designer's perusal.
5. `cds.lib` - The file used by Virtuoso to index library locations, to access them.

### Documentation:  
    1. gpdk90 MOS model file: ./libs/gpdk090_v4.6/models/spectre/gpdk090_mos.scs  
    2. gpdk90 Design Rule Manual: ./libs/gpdk090_v4.6/docs/gpdk090_DRM.pdf  
    3. gpdk90 Reference Manual: ./libs/gpdk090_v4.6/docs/gpdk090_pdk_referenceManual.pdf  
    4. Spectremod (simulator used by ADE L) manual: /opt/IC617/doc/spectremod/spectremod.pdf (look into Pg. 1221 "Operating Point Parameters" for definitions of MOSFET operating point parameters)  
    5. Analoglib manual: /opt/IC617/doc/analoglibref/analoglibref.pdf  
    6. Literally any other doc: /opt/IC617/doc/  

### RHEL Environment:  
To activate sudo permission:  

    su root # enter password  
    usermod -aG wheel work # and then edit /etc/sudoers file by removing the comment (# symbol) in front of: # %wheel ALL=(ALL) ALL  
    exit  
    exit # then log out and log in again, you will be able to invoke sudo
    
To change time-zone, date, and time:  

    # Use the following GUI approach to change time settings  
    system-config-date  
    
    # OR, use following cmd-line approach:
    
    # Change timezone:
    ls /usr/share/zoneinfo # Check for /etc/share/zoneinfo/Asia/Kolkata
    sudo nano /etc/sysconfig/clock # Change contents to ZONE="Asia/Kolkata"
    tzdata-update
    sudo ln -sf /usr/share/zoneinfo/Asia/Kolkata /etc/localtime
    date # To verify timezone, date, and time
    
    # Change date, time:
    sudo date +%D -s YYYY-MM-DD # Replace YYYY-MM-DD with current date
    sudo date +%T -s HH:MM:SS # Replace HH:MM:SS with current time
    date # Verify date, time

## Project:  

### References:  
1. [A 10 nW–1 μW Power Management IC With Integrated Battery Management and Self-Startup for Energy Harvesting Applications]  
2. 
[A 10 nW–1 μW Power Management IC With Integrated Battery Management and Self-Startup for Energy Harvesting Applications]: https://ieeexplore.ieee.org/document/7366755

