# IsaacLab-Tools
A browser themed VSCode extension and some other tools for training robots with Isaac Lab both locally and with cloud computing

<img width="2784" height="1638" alt="image" src="https://github.com/user-attachments/assets/7152d1c0-9fcc-41f9-895b-4c8604e0de94" />

A good cloud computing service that that used while developing the remote tab features is Vast.ai, using this template here: 
https://cloud.vast.ai?ref_id=504182&template_id=e25452f60c8fe45d982518bf3c988d94

The VSCode extension has 3 types of tabs: the File Explorer, the Training tab, and the Remote Instance tab
The user can add as many of each tab as they want, enabling multiple parallel training sessions, connecting to multiple different remote machines, etc

File Explorer tabs auto-detects Isaac installations if they exist but the user can manually browse for an installation (the folder simply called "Isaac". The user can navigate their Isaac folders, write new scripts, delete files, and even edit files in the extension. 

<img width="2784" height="1640" alt="image" src="https://github.com/user-attachments/assets/fd3d18a0-27f8-4116-a285-8484f0758cf9" />

The Training tab is a built-in mini Windows Powershell, with dedicated buttons to run scripts, stop scripts, and enable/disable virtual environments with a single click. The Training tab also has an Isaac installer, handling the installation, uninstallation, and verification of your local Isaac instance (may be buggy for now, probably needs to be more robust).

<img width="2782" height="1582" alt="image" src="https://github.com/user-attachments/assets/4a0895d1-fea5-434d-8210-0ffd87ec9502" />

The Remote Instance tab is intended for Isaac training using rented remote machines. This tab also has a built-in Powershell. This tab has options to generate your SSH key and retrieve other local machine info. Once you rent your remote machine, just input the IP and port, and this tab has its own Isaac installer for the remote machine. Once connected and remote Isaac installed, there's a pseudo-File Explorer for the user to access the files in the remote workspace, allowing the user to import and export files between the local and remote machines, and editing the remote workspace. 

<img width="2784" height="1630" alt="image" src="https://github.com/user-attachments/assets/c487a4ff-503d-425d-a578-6dd4b0459dca" />

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

*All local Isaac installations through the extension have the same hardware and software requirements as the installation through other means
(pip, python (I use 3.10 with Isaac Lab 4.5), Git, etc)

More features to come...
