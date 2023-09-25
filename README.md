# GUI Based Folder Locker Application System

//Brief explanation of the Java code 

In this repository the  folder locker application with a graphical user interface (GUI) built using Swing. This application allows users to lock and unlock folders by encrypting and decrypting their contents. Let's break down the code and elaborate on each part:



Import Statements: The code starts by importing necessary Java libraries and classes for GUI development, file handling, and encryption.

Class Definition: The folderLockGUI class extends JFrame to create the main application window.

Instance Variables:

folderPathField: A JTextField for users to enter the path of the folder they want to lock/unlock.

lockButton and unlockButton: JButton components for locking and unlocking the folder.

SALT: A static byte array used as salt for password-based encryption.

Constructor:

The constructor sets up the main window's properties, such as title, size, and location.
It initializes the GUI components (text field, buttons) and adds action listeners to the lock and unlock buttons.
lockFolder Method:

This method is called when the "Lock Folder" button is clicked.

It validates the folder path, checks if files exist in the folder, and prompts the user for a password.

If a password is provided, it creates a cipher with encryption mode and encrypts each file in the folder, appending the ".locked" extension.
After encryption, the original files are deleted, and a success message is displayed.

unlockFolder Method:

This method is called when the "Unlock Folder" button is clicked.
It validates the folder path, checks for ".locked" files in the folder, and prompts the user for a password.
If the correct password is provided, it creates a cipher with decryption mode and decrypts each ".locked" file, removing the ".locked" extension.
After decryption, the locked files are deleted, and a success message is displayed.


getCipher Method:

This method initializes and returns a Cipher object for encryption or decryption using a provided password.


encryptFile Method:

This method encrypts a file using the given cipher and saves it with a ".locked" extension.


decryptFile Method:

This method decrypts a ".locked" file using the given cipher and removes the ".locked" extension from the file name.
main Method:

The main method is the entry point of the program.
It creates an instance of the folderLockGUI class and sets it to be visible in the Event Dispatch Thread (EDT) using SwingUtilities.invokeLater.


To use this folder locker application:

Compile the code and run it.

Enter the folder path you want to lock/unlock.

Provide a password when prompted.

Click the "Lock Folder" button to lock the folder or the "Unlock Folder" button to unlock it.



