Switch Upgrade Automation Script
This repository contains a Python script designed to automate the process of upgrading Dell OS10 switches. The script connects to a list of switches, configures them to use VRF management for SFTP, installs a specified image, and performs a series of post-installation tasks such as setting the boot partition and reloading the switch.

Features
Automated SFTP Configuration: The script automatically configures SFTP to use VRF management on each switch.
Firmware Installation: It installs a specified firmware image on each switch, checking the installation status until completion.
Boot Partition Management: After installing the firmware, the script switches the boot partition to partition B.
Switch Reload: The script reloads the switch to apply the changes.
Excel Integration: Devices are read from an Excel file, making it easy to manage and update the list of switches to be upgraded.
Prerequisites
Before running the script, ensure you have the following installed:

Python 3.x
Required Python packages: pandas, netmiko, openpyxl (for reading Excel files)
You can install the necessary packages using pip:

sh
Copy code
pip install pandas netmiko openpyxl
Usage
Prepare the Excel File: Create an Excel file (devices.xlsx) with the following columns:

IP: The IP address of the switch.
Username: The username for SSH login.
Password: The password for SSH login.
Update the Install Command: Modify the install_command variable in the script to reflect the correct SFTP path and credentials for your environment.

Run the Script:

sh
Copy code
python upgrade_script.py
The script will read the list of devices from the Excel file and perform the upgrade process on each one.

Error Handling
The script includes basic error handling to catch and display any issues that arise during the upgrade process. If an error occurs, the script will print the error message and continue to the next device.

Debugging
For debugging purposes, the script prints the output of each major command, allowing you to see what’s happening at each step.

Contribution
Feel free to fork this repository, submit pull requests, or open issues if you encounter any problems or have suggestions for improvements.

License
This project is licensed under the MIT License. See the LICENSE file for details.
