## Aspera or FTP file upload

Once your submission files have been prepared using the PX Submission Tool, files can be uploaded using Aspera or FTP. When preparing your dataset please be sure to unambiguously assign a unique file name to all of your files. Please also upload the submission summary file and the checksum file (both generated by PX tool) into the same folder.

First, ask PRIDE support (at pride-support@ebi.ac.uk) for a target directory and a password. The PRIDE curators will specify a target directory for you, see <name-oftarget-dir-specified-by-PRIDE> in the following commands, and you will be provided with this information. Please E-mail us once your upload has been successfully finished.

## Aspera 

### Install Aspera ascp command line programme

Aspera is a commercial file transfer protocol that may provide faster transfer speeds than ftp especially over longer distances.

Operating System: Windows XP / 2003 / Vista / 2008 / 7 / 8, Mac OS Intel 10.5 / 10.6 / 10.7 / 10.8 / Linux

The Aspera ascp command line client can be downloaded [here](http://downloads.asperasoft.com/downloads).

Please select **Aspera Connect**.

The ascp command line client is distributed as part of the aspera connect high-performance transfer browser plug-in and is free to use, without registration. 

The location of the 'ascp' program in the filesystem:

 - Mac: On the desktop go `cd /Applications/Aspera\ Connect.app/Contents/Resources/` there you'll see the command line utilities where you're going to use 'ascp'.

 - Windows: The downloaded files are a bit hidden. For instance in Windows 7 the ascp.exe is located in the users home directory in: `AppData\Local\Programs\Aspera\Aspera Connect\bin\ascp.exe`

 - Linux: It should be in your user's home directory, `cd /home/username/.aspera/connect/bin/` there you'll see the command line utilities where you're going to use 'ascp'.

### Using the Aspera ascp command line program

Your command should look similar to this:    

- Mac/Linux: `ascp -P33001 -QT -l300M L --file-manifest=text -k2 -o Overwrite=diff <path-tofolder-to-be-uploaded> pride-drop-006@hx-fasp-1.ebi.ac.uk:/<name-of-target-dir-specified-by-PRIDE>`

- Windows: `ascp.exe -P33001 -QT -l300M L --file-manifest=text -k2 -o Overwrite=diff <path-tofolder-to-be-uploaded> pride-drop-006@hx-fasp-1.ebi.ac.uk:/<name-of-target-dir-specified-by-PRIDE>`

### Explanation of parameters

- **-l500M** option sets the upload speed limit to 500MB/s. You may wish to lower this value if you get timeout issues or to increase the reliability of the transfer.

- **L** option is for printing logs out while transferring

- **path-to-folder-to-be-uploaded** directory with the files to be submitted.

- **name-of-target-dir-specified-by-PRIDE** directory name provided by PRIDE.

- Add **-k2** switch for transfer restarts

Check the command line transfer [usage](http://download.asperasoft.com/download/docs/ascp/2.7/html/index.html) for more configuration details. 

Please provide the password when it prompt. This will generate an Aspera progress file on your side that will contain a report on the files that have been uploaded, also you can interrupt the process and then it will only upload the ones that were not there so no more overwriting files. It will also skip the ones that are already in the target directory.

## FTP 

PRIDE team will setup a directory on our private FTP server for you to manually upload your files to. Please see the details below:

FTP details:

- FTP server: ftp-private.ebi.ac.uk
- User name : pride-drop-006
- Password : <password>
- directory : <name-of-target-dir-specified-by-PRIDE>

For security reasons, we do not allow directory listings at the top level so you will need to manually navigate to the proper directory, either by typing the command (if using a command-line): `cd <Directory Name>`
or by the corresponding "go to directory" option (of whatever graphical tool you are using): `/<Directory Name>`

Concerning FTP client programs, we recommend using WinSCP (Windows only) or FileZilla (all OS). You can download one of them from these links:
- WinSCP : http://winscp.net/eng/download.php
- FileZilla: http://filezilla-project.org/download.php

Once connected to the FTP and in your target directory, upload your files normally, and let me know when the transfer has been completed.
    
### Using an FTP client

e.g. Filezilla

Use the following connection details (File=> Site Manager) and add your submission account username and password :

![FTP upload](../markdown/submissionupload/files/filezilla.png)

Select the files you wish to upload, then right click mouse, and select 'upload'.