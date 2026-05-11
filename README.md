# IsaacLab-Tools
A browser themed VSCode extension and some other tools for training robots with Isaac Lab both locally and with cloud computing

<img width="2784" height="1638" alt="image" src="https://github.com/user-attachments/assets/7152d1c0-9fcc-41f9-895b-4c8604e0de94" />

A good cloud computing service that that used while developing the remote tab features is Vast.ai, using this template here: 
https://cloud.vast.ai?ref_id=504182&template_id=dc479b41b7dfd6056db0db892a75eaa1

The VSCode extension has 4 types of tabs: the File Explorer, the Training tab, the Remote Instance tab, and the Training Monitor tab.
The user can add as many of each tab as they want, enabling multiple parallel training sessions, connecting to multiple different remote machines, etc

File Explorer tabs auto-detects Isaac installations if they exist but the user can manually browse for an installation (the folder simply called "Isaac". The user can navigate their Isaac folders, write new scripts, delete files, and even edit files in the extension. 

<img width="2782" height="1630" alt="image" src="https://github.com/user-attachments/assets/734f6812-c13f-4fe8-a01d-8964b041a42f" />


The Training tab is a built-in mini Windows Powershell, with dedicated buttons to run scripts, stop scripts, and enable/disable virtual environments with a single click. The Training tab also has an Isaac installer, handling the installation, uninstallation, and verification of your local Isaac instance (may be buggy for now, probably needs to be more robust).

<img width="2782" height="1582" alt="image" src="https://github.com/user-attachments/assets/4a0895d1-fea5-434d-8210-0ffd87ec9502" />

The Remote Instance tab is intended for Isaac training using rented remote machines. This tab also has a built-in Powershell. This tab has options to generate your SSH key and retrieve other local machine info. Once you rent your remote machine, just input the IP and port, and this tab has its own Isaac installer for the remote machine. Once connected and remote Isaac installed, there's a pseudo-File Explorer for the user to access the files in the remote workspace, allowing the user to import and export files between the local and remote machines, and editing the remote workspace. 

<img width="2782" height="1636" alt="image" src="https://github.com/user-attachments/assets/6acd2ba5-819b-4f78-897e-116ae5a71c09" />

Steps for remote training:

1.) Generate SSH key on local machine using VSCode extension

2.) Rent remote machine for desired GPU (using above linked template for simplicity)

  -Some additional setup may be needed server side depending on the service
  
3.) Input remote machine access IP and port into Remote Instance tab

4.) Install Isaac Lab on remote machine using extention's Remote Instance: Installation Tools

5.) Export your training scripts, robot configs, etc for your needs to the remote machine

6.) Run your training scripts! 

  -Import your trained policies back to your local machine after training

*If needed, the Powershell for both training and remote instance tabs is always available to run custom commands that may not be built-in yet

The Training Monitor tab is extremely useful, especially for the remote instance training when you may not be able to view the UI. This tab pretty much plots all of your important training information over iterations as shown. When this monitor is coupled with my training script package, it gets extremely powerful, with the monitor calculating accurate ETAs, plotting individual rewards, and more!

<img width="2766" height="1634" alt="image" src="https://github.com/user-attachments/assets/e271e3e6-1c15-4411-9155-9ce900f43cd5" />

<img width="2774" height="1632" alt="image" src="https://github.com/user-attachments/assets/decf9bce-a392-4d95-81f0-34b9f2be6d9e" />

*All local Isaac installations through the extension have the same hardware and software requirements as the installation through other means
(pip, python (I use 3.10 with Isaac Lab 4.5), Git, etc)

More features to come...
