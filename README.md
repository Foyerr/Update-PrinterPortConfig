# Printer-Port-Configuration
Windows Print Server Port & IP Misconfiguration Fix

## Purpose
After going through a network migration, printer ports may be mislabeled, making it difficult to determine which IP is assigned to which printer at a glance. This repository contains PowerShell functions to automate the process of fixing these misconfigurations.

## Description
The script will search through your print server's registry for all printers with differing port names compared to their actual IPs. It will then correct the issue by renaming the port name in the registry to the correct IP and renaming the monitor key to the correct IP as well.

### Functions

#### BackUp-Registry
- **Synopsis**: Backs up specific registry keys related to printers and port monitors to the current directory.
- **Usage**: `BackUp-Registry`

#### Get-PrinterIP
- **Synopsis**: Retrieves the IP addresses associated with printers and returns them in a custom object list.
- **Usage**: `$printerList = Get-PrinterIP`

#### Set-PrinterIP
- **Synopsis**: Updates the IP addresses of printers based on a provided list of printer details.
- **Usage**: `Set-PrinterIP $printerList`
- **Parameters**: 
  - `printerList`: Specifies the list of printers with details to be updated.

### Requirements
- Windows PowerShell 5.1 
- Administrative privileges 

### Examples

#### BackUp-Registry
```
# Get the printer list from the print server
$printerList = Get-PrinterIP

# Update the registry to the correct IP
Set-PrinterIP $printerList

# Restart Spooler for the changes to apply
Restart-Service -Force Spooler -confirm
```
## Example of the issue:

![image](https://user-images.githubusercontent.com/43224440/149582787-4cb00cac-e570-4fa5-ac66-25b77ab8fffb.png)


