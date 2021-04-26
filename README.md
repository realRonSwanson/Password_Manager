# Password_Manager
Pass123: Application for storing/viewing/and generating secure passwords stored on a USB drive

This application implements quite a few layers of security to protect the user's stored credentials.
We strongly recommend following all of the guidelines referenced in the available User Manual.

This application was written in python and intended for the Microsoft Windows OS.
Pass123 implements multi factor authentication through the use of a master password as well as a secret key.
The key is intended to be separated from the USB drive to secure the stored passwords from being decrypted should someone get ahold of the drive.
The key is generated and used to decrypt/encrypt via python's Fernet cryptography module
If this key is deleted or misplaced, none of the contained passwords will be accessible

We have provided the python code for generating secrety keys in the main repository

Upon initial startup, the user will be prompted to create a master password that they will use for each sequential use of the Pass123 application.
This master password cannot be changed and should be something that only the user has access to. 
Should someone attempt to change the master password file in order to bypass authentication, the application will not run because the code searches for a specific string within the master password file. The code also requires that the password file is not encrypted in order to allow the the master password to be created. Manipulation of either text files will not provide any credentials in clear text or allow the application to run.

It can be adapted to run on Mac and Linux OS by changing the os.system commands to the OS equivalent for your specific situation.
Pyinstaller can be used to easily compile the code into an executable format.



