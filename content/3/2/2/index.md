---
canonical: "https://jsandtsmastery.com/3/2/2"
title: "Installing Visual Studio Code: A Step-by-Step Guide for Beginners"
description: "Learn how to install Visual Studio Code on Windows, macOS, and Linux with this comprehensive guide. Includes system requirements, troubleshooting tips, and screenshots."
linkTitle: "2.2 Installing Visual Studio Code"
categories:
- Web Development
- JavaScript
- Programming
tags:
- Visual Studio Code
- VSCode Installation
- Development Environment
- Windows
- macOS
- Linux
date: 2024-10-25
type: docs
nav_weight: 2200
license: "© 2024 Tokenizer Inc. CC BY-NC-SA 4.0"
---

## 2.2 Installing Visual Studio Code

Welcome to the exciting journey of building your first web page with JavaScript! Before we dive into coding, we need to set up our development environment. One of the most popular and powerful tools for writing code is Visual Studio Code (VSCode). In this section, we'll walk you through the process of installing VSCode on different operating systems: Windows, macOS, and Linux. We'll also cover system requirements and provide troubleshooting tips for common installation issues.

### Why Choose Visual Studio Code?

Visual Studio Code is a free, open-source code editor developed by Microsoft. It is lightweight yet powerful, offering a range of features that make it an excellent choice for web development:

- **Intelligent Code Completion**: VSCode provides smart suggestions and auto-completion to speed up your coding process.
- **Built-in Git Support**: Easily manage your code versions with integrated Git commands.
- **Extensions Marketplace**: Customize your editor with thousands of extensions for different languages and tools.
- **Debugging Tools**: Debug your code directly within the editor.
- **Cross-Platform**: Available for Windows, macOS, and Linux.

### System Requirements

Before installing VSCode, ensure your system meets the following minimum requirements:

- **Windows**: Windows 7, 8, 10, or 11 (64-bit recommended)
- **macOS**: macOS 10.11 or later
- **Linux**: Ubuntu 16.04+, Debian 9+, Fedora 30+, or any other distribution with GLIBC 2.17+

### Installing Visual Studio Code on Windows

Let's start with the installation process on Windows. Follow these steps to get VSCode up and running:

#### Step 1: Download Visual Studio Code

1. Open your web browser and navigate to the [Visual Studio Code download page](https://code.visualstudio.com/Download).
2. Click on the **Windows** download link. This will download the installer file (`.exe`) to your computer.

![Download VSCode for Windows](https://code.visualstudio.com/assets/docs/editor/why-vscode/hero.png)

#### Step 2: Run the Installer

1. Locate the downloaded `.exe` file in your `Downloads` folder or wherever you saved it.
2. Double-click the file to start the installation process.

#### Step 3: Accept the License Agreement

1. Read through the license agreement.
2. Check the box to accept the terms and click **Next**.

#### Step 4: Choose Installation Location

1. Choose the destination folder where you want to install VSCode. The default location is usually fine.
2. Click **Next** to continue.

#### Step 5: Select Additional Tasks

1. You can choose to create a desktop icon and add VSCode to your PATH. These options are recommended for easier access.
2. Click **Next** and then **Install** to begin the installation.

![VSCode Installation Options](https://code.visualstudio.com/assets/docs/editor/why-vscode/hero.png)

#### Step 6: Launch Visual Studio Code

1. Once the installation is complete, check the box to launch Visual Studio Code.
2. Click **Finish** to open VSCode.

### Installing Visual Studio Code on macOS

For macOS users, the installation process is slightly different. Follow these steps:

#### Step 1: Download Visual Studio Code

1. Visit the [Visual Studio Code download page](https://code.visualstudio.com/Download).
2. Click on the **macOS** download link. This will download a `.zip` file.

![Download VSCode for macOS](https://code.visualstudio.com/assets/docs/editor/why-vscode/hero.png)

#### Step 2: Extract the Archive

1. Open your `Downloads` folder and locate the downloaded `.zip` file.
2. Double-click the file to extract its contents.

#### Step 3: Move to Applications

1. Drag the extracted `Visual Studio Code.app` file into your `Applications` folder.

#### Step 4: Open Visual Studio Code

1. Navigate to your `Applications` folder.
2. Double-click `Visual Studio Code` to launch the editor.

#### Step 5: Grant Permissions

1. If prompted, confirm that you want to open the application downloaded from the internet.

### Installing Visual Studio Code on Linux

For Linux users, the installation process varies slightly depending on your distribution. We'll cover the steps for Ubuntu/Debian and Fedora:

#### Ubuntu/Debian

##### Step 1: Update Package Index

Open your terminal and run the following command to update your package index:

```bash
sudo apt update
```

##### Step 2: Install Dependencies

Ensure you have the necessary dependencies installed:

```bash
sudo apt install software-properties-common apt-transport-https wget
```

##### Step 3: Add Microsoft GPG Key

Run the following command to import the Microsoft GPG key:

```bash
wget -q https://packages.microsoft.com/keys/microsoft.asc -O- | sudo apt-key add -
```

##### Step 4: Enable VSCode Repository

Add the VSCode repository to your sources list:

```bash
sudo add-apt-repository "deb [arch=amd64] https://packages.microsoft.com/repos/vscode stable main"
```

##### Step 5: Install Visual Studio Code

Now, install VSCode using the following command:

```bash
sudo apt install code
```

#### Fedora

##### Step 1: Import Microsoft GPG Key

Open your terminal and run:

```bash
sudo rpm --import https://packages.microsoft.com/keys/microsoft.asc
```

##### Step 2: Add VSCode Repository

Create a new repository file:

```bash
sudo sh -c 'echo -e "[code]\nname=Visual Studio Code\nbaseurl=https://packages.microsoft.com/yumrepos/vscode\nenabled=1\ngpgcheck=1\ngpgkey=https://packages.microsoft.com/keys/microsoft.asc" > /etc/yum.repos.d/vscode.repo'
```

##### Step 3: Install Visual Studio Code

Use the following command to install VSCode:

```bash
sudo dnf install code
```

### Troubleshooting Common Installation Issues

Even with the best instructions, sometimes things don't go as planned. Here are some common issues and how to resolve them:

#### Issue 1: Installation Fails on Windows

- **Solution**: Ensure you have administrative privileges. Right-click the installer and select "Run as administrator."

#### Issue 2: VSCode Won't Launch on macOS

- **Solution**: Check your security settings. Go to `System Preferences > Security & Privacy` and allow apps from identified developers.

#### Issue 3: Package Not Found on Linux

- **Solution**: Double-check that you've added the repository correctly and updated your package index.

### Try It Yourself

Now that you have VSCode installed, let's try a simple exercise:

1. Open Visual Studio Code.
2. Create a new file by clicking `File > New File`.
3. Type the following code:

```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Hello, World!</title>
</head>
<body>
    <h1>Hello, World!</h1>
</body>
</html>
```

4. Save the file as `index.html`.
5. Open the file in your web browser to see your first web page!

### Summary

In this section, we've covered the installation of Visual Studio Code on Windows, macOS, and Linux. We've also discussed system requirements and provided troubleshooting tips for common issues. With VSCode installed, you're now ready to start building your first web page with JavaScript!

## Quiz Time!

{{< quizdown >}}

### Which operating systems support Visual Studio Code?

- [x] Windows
- [x] macOS
- [x] Linux
- [ ] Android

> **Explanation:** Visual Studio Code is available for Windows, macOS, and Linux. It is not available for Android.

### What is the minimum macOS version required to install Visual Studio Code?

- [ ] macOS 10.9
- [ ] macOS 10.10
- [x] macOS 10.11
- [ ] macOS 10.12

> **Explanation:** The minimum macOS version required to install Visual Studio Code is macOS 10.11.

### What command is used to add the Microsoft GPG key on Ubuntu/Debian?

- [x] `wget -q https://packages.microsoft.com/keys/microsoft.asc -O- | sudo apt-key add -`
- [ ] `sudo apt-get install microsoft-key`
- [ ] `sudo add-key microsoft`
- [ ] `wget https://microsoft.com/key`

> **Explanation:** The correct command to add the Microsoft GPG key on Ubuntu/Debian is `wget -q https://packages.microsoft.com/keys/microsoft.asc -O- | sudo apt-key add -`.

### What should you do if VSCode won't launch on macOS?

- [ ] Reinstall macOS
- [x] Check security settings and allow apps from identified developers
- [ ] Download a different code editor
- [ ] Restart your computer

> **Explanation:** If VSCode won't launch on macOS, you should check your security settings and allow apps from identified developers.

### Which command installs VSCode on Fedora?

- [ ] `sudo apt install code`
- [x] `sudo dnf install code`
- [ ] `sudo yum install vscode`
- [ ] `sudo pacman -S code`

> **Explanation:** The command to install VSCode on Fedora is `sudo dnf install code`.

### What is the default installation location for VSCode on Windows?

- [ ] C:\Program Files (x86)\VSCode
- [x] C:\Program Files\Microsoft VS Code
- [ ] C:\Users\YourName\VSCode
- [ ] C:\Windows\VSCode

> **Explanation:** The default installation location for VSCode on Windows is `C:\Program Files\Microsoft VS Code`.

### Which file format is used to download VSCode for macOS?

- [ ] .exe
- [x] .zip
- [ ] .tar.gz
- [ ] .dmg

> **Explanation:** VSCode for macOS is downloaded as a `.zip` file.

### What is the purpose of adding VSCode to your PATH on Windows?

- [ ] To increase system performance
- [x] To allow running VSCode from the command line
- [ ] To enable automatic updates
- [ ] To improve security

> **Explanation:** Adding VSCode to your PATH on Windows allows you to run VSCode from the command line.

### What should you do if the VSCode package is not found on Linux?

- [ ] Reinstall Linux
- [x] Check if the repository is added correctly and update the package index
- [ ] Download VSCode from a different website
- [ ] Use a different code editor

> **Explanation:** If the VSCode package is not found on Linux, you should check if the repository is added correctly and update the package index.

### True or False: Visual Studio Code is a paid software.

- [ ] True
- [x] False

> **Explanation:** Visual Studio Code is a free, open-source code editor developed by Microsoft.

{{< /quizdown >}}
