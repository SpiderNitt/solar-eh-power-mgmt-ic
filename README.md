# solar-eh-power-mgmt-ic
This project aims to create the schematic and layout files (and perform simulation) of a power management IC for solar energy harvesting applications.

To activate sudo permission in RHEL:
su root # enter password 111111 
usermod -aG wheel work # and then edit /etc/sudoers file by removing the comment (# symbol) in front of: # %wheel ALL=(ALL) ALL
su work
exit # then log out and log in again, you will be able to invoke sudo

Documentation and Models
gpdk90 MOS model file: /home/work/solar_eh_pmic/gpdk090_v4.6/models/spectre/gpdk090_mos.scs
gpdk90 Design Rule Manual: ./gpdk090_v4.6/docs/gpdk090_DRM.pdf
gpdk90 Reference Manual: ./gpdk090_v4.6/docs/gpdk090_pdk_referenceManual.pdf
Spectremod (simulator used by ADE L) manual: /opt/IC617/doc/spectremod/spectremod.pdf (look into Pg. 1221 "Operating Point Parameters" for definitions of MOSFET operating point parameters)
Analoglib manual: /opt/IC617/doc/analoglibref/analoglibref.pdf
Literally any other doc: /opt/IC617/doc/

General Instructions:
Make sure your working directory is /home/work/solar_eh_pmic/, and then type "virtuoso" in terminal. In this directory only all libraries, etc. are present, and also simulation states assume this to be the working directory
To change simulation directory, in Virtuoso go to Tools>ADE L>Setup>Simulator/Directory/Host. Here, under "Change project directory", enter /home/work/solar_eh_pmic/simulation/SIM_IC61

