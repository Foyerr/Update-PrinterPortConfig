# Printer-Port-Configuration
Windows Print Server Port & IP Misconfiguration Fix

## Purpose
  After going through a network migration, printer ports have been mislabeled making it diffcult to tell what IP is assigned to what printer at glance.
  
## Description
  This script will seach though your print server's registry for all printers with differeing portname compared to their IP's. 
  It will then correct the issue by renaming the portname in registry to the correct IP and then renaming the monitor key to the correct IP as well.

  A spooler restart will be required afterwards.

  This takes all of the manual work out of creating new ports after a misconfigureation

## Example of the issue:

![image](https://user-images.githubusercontent.com/43224440/149582787-4cb00cac-e570-4fa5-ac66-25b77ab8fffb.png)


