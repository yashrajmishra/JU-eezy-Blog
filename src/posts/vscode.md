---
title: "Installation and Setup for VS Code"
path: "/vscode"
date: "2019-02-18"
author: "Atul Sharma"
excerpt: "Having tough time installing VS Code, Maybe I can help....."
tags: ["vscode","gcccompiler","chocolatey","coderunner"]
---

## Let's Install VS Code

![](https://raw.githubusercontent.com/Iltwats/CDN/master/image/installtion&setup.jpg)

**Which is the best source code editor available right now? Without no doubt, we can say that it’s Visual Studio code or simply VS code. VS code is an open-source code editor developed by Microsoft.**

**It has built-in support for C++, JavaScript, Node.js and almost all programing language-based plugins are available in VS studio right now.Let`s install the stable version of VS code on our Windows system**

---

### Steps

- VS code setup file can be downloaded from the official website. Link is given- [https://code.visualstudio.com/](https://code.visualstudio.com/).
  
  ![](https://raw.githubusercontent.com/Iltwats/CDN/master/image/vsdownload.jpg)

- After opening the website, click on the **Download for Windows** button. This will download the VS code Setup Wizard on our system as an EXE file.

- So, the VS code Setup Wizard is downloaded successfully, and we need to run it.
  
  1. Click on the setup file, a preview has been shown: -

            ![](https://raw.githubusercontent.com/Iltwats/CDN/master/image/setup1.jpg)

       2. Agree to the License Agreement,

       3.Select the Installation Location,

       4. Placing the Shortcuts,

       5. Selecting Additional Tasks, select all the options as shown in preview (all not mandatory but should be added to path).

![](https://raw.githubusercontent.com/Iltwats/CDN/master/image/setup2.jpg)

      6.Now, click on Next then **install** the VS code.

      7.After the successful installation Launch the VS code on your system now.

---

### Installing the Compiler(GCC)

- Open Windows PowerShell as run as administrator and type the following statement in it and press enter. (Copy exact code from below):

- ```powershell
  Set-ExecutionPolicy Bypass -Scope Process -Force; iex ((New-Object System.Net.WebClient).DownloadString('https://chocolatey.org/install.ps1'))
  ```

- The Chocolatey package manager for windows is installed in your PC.To use chocolatey restart PowerShell in **Administrator Mode**.

- After restarting just type the following into the Powershell and press enter.

- ```powershell
  choco install mingw
  ```

- This is the preview of what it might look like:
  
  ![](https://raw.githubusercontent.com/Iltwats/CDN/master/image/install.png)

- When asked 'Do you want to run the script' type **A** as yes to all.

- Then enter *refreshenv* the refresh the environment variable and close the shell, your **GCC Compiler** has been installed and added to path successfully.

- Also you can use chocolatey to install different compilers and packages and to check those out visit [https://chocolatey.org/packages](https://chocolatey.org/packages) and find relevant packages as per your need.

- Like to install python or javascript type the following in PowerShell(administrator):

- ```powershell
  choco install python
  choco install nodejs
  ```

---

### Now Setting Up the VS code

Writing your first code running it-

- Launch VS Code.

- Type in your first `Hello World` program to run it. Also in the meantime you can check the the version of compiler by typing the following in the terminal of VS Code:

- ```powershell
  gcc --version
  ```

![](https://raw.githubusercontent.com/Iltwats/CDN/master/image/fix1.jpg)

- Now to run the following program we must install **Code-Runner**, go to marketplace (has been encircled in preview) and search for it:

![](https://raw.githubusercontent.com/Iltwats/CDN/master/image/fix2.jpg)

- After you have installed go to *Code Runnner extension`s* settings:

![](https://raw.githubusercontent.com/Iltwats/CDN/master/image/fix3.png)

- Then check the following boxes (**Run in terminal**) so that you can take input in your programs from the settings menu of Code-Runner down the page-

![](https://raw.githubusercontent.com/Iltwats/CDN/master/image/fix4.jpg)

- After this last step is to install extensions for various programming languages, here we will install C++ extensions from the marketplace. I recommend *C/C++ by Microsoft*.

![](https://raw.githubusercontent.com/Iltwats/CDN/master/image/fix5.jpg)

- Now we will run our program, go to your `HelloWorld` Program and either press(***Ctrl+Alt+N***) or the run button at the top right section of the page to run your program and to get the desired output:

![](https://raw.githubusercontent.com/Iltwats/CDN/master/image/fix6.jpg)

- We always get the output in terminal window.

---

### Few points to consider

- Using Chocolatey Package Installer for installing compiler nullify the mistake of installing wrong architecture compiler when done manually.

- For VS code keyboard shortcuts please visit the following link: [https://code.visualstudio.com/shortcuts/keyboard-shortcuts-windows.pdf](https://code.visualstudio.com/shortcuts/keyboard-shortcuts-windows.pdf)

- For compiling programs for other language please install proper extensions for the language and the compiler beforehand.

- If you get any other error like .exe file not compatible with your system architecture, please contact me on **[Atul Sharma](mailto:atul.19bcon231@jecrcu.edu.in?Subject=Doubt%20query)** for further clarification.
