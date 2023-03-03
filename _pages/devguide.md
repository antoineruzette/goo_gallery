---
title: Developer's Guide
subtitle: Goo is an open and collaborative project started in Sean Megason's group at Harvard University. We welcome everyone who is interested in enhancing 3D models of biological cells with Blender. The developer’s guide is to help contributors willing to start working and contributing on Goo. If you are interested in join, please contact Sean Megason - sean_megason AT hms harvard edu.
description: ''
featured_image: ''
---

<h3>Git/Github</h3>
The first thing you need to do is to fork the Goo repository and then clone the forked repository into your local machine. This will give you the freedom to test and make changes to the project without affecting the original repository.

Make sure you have git installed on your local machine. If you do not have it install on your system, refer to this <a href="https://github.com/git-guides/install-git">guide</a>.

<h5>Fork & clone</h5>
If you are new to Git/Github, refer to this <a href="https://docs.github.com/en/get-started/quickstart/fork-a-repo">guide</a> to learn how to fork and clone a repository from Github: 

<h5>Push</h5>
Once you make final changes and the scripts run with no issues, you can push them into the main project. Here is an instruction on how to push using git.

<h3>Blender</h3>
Blender is an amazing open-source and free 3D computer graphics software, widely used in motion design, graphism, animation, and becoming increasingly popular in sciences. Its Python API comes handy for developers willing to extend Blender's capabilities, much like Goo does. Blender has a huge community and contributors all over the world, which gathers every year at Blender convention and every day on the Blender community discord. 

Once you have downloaded and installed Blender, launch Blender and select General to open a new file. The scripting tab allows you to interact with Blender using Python. By clicking scripting, a list of windows will open:

1. 3D Viewport allows you to interact with 3D objects.
2. Python Interactive Console allows you to interact with Blender using Python language.
3. Info Console Menu or Report console creates a log in Python of the executed actions on Blender. In another words, it translates the clicks you made in Blender into code. This is very useful especially when you try to automate procedures of actions on scripting.

<h5>Creating Python File</h5>
You can create a Python file and run it on Blender. Once you are in Scripting tab, click on the + New icon.

Blender Python’s API, named bpy, allows Python and Blender to fit together. To use it, the following package should be imported:

import bpy

The Blender API can used with no installation nor importing into the Python Interactive Console. The Python file can be run on Blender by clicking on play icon.

<h5>Viewing Python Error Messages</h5>
PC: Window -> Toggle System Console

Mac: Finder -> Applications -> right-click on Blender -> Show Package Content -> Contents -> MacOS -> right-click on Blender -> Make Alias. Blender will be launched by double-clicking the Blender alias and any error messages will display on the alias window. You can store the alia any folder.

<h5>Blender Python Tutorials</h5>
You can find many free tutorials on YouTube and the Internet. here is a great tutorial, made by Darkfall, on YouTube on how to write a Python script in Blender.

</h5>Useful Blender Tips</h5>
To Display Line Numbers on a Python file, click View and mark the checkbox of Line Numbers. View tab will appear once you create a Python file.

To turn on Highlight Line at the line currently at, click View and mark the checkbox of Highlight Line. View tab will appear once you create a Python file.

Developer Extras allows users to examine Python codes on any features or buttons on Blender by right-clicking for example on a Render button and then select Edit Source. To enable this Developer Extras, go to Edit -> Preferences -> Interface -> check Developer Extras

Python Tooltips also allows users to examine the Python codes behind any bulit-in Blender features by just hovering the mouse on top and a pops-up window will appear. To enable Python Tooltips, Edit -> Preferences -> Interface -> Check Python Tooltips

<h3>Visual Studio Code (VSCode)</h3>
You can use any IDE softwares (Atom, PyCharm, Anaconda,…etc) available on the internet, but from our experience Visual Studio Code has been very smooth and convenient to use.

<h5>Getting started with VSCode:</h5>
Install Python - Make sure you have Python already installed in your machine. If you are not sure, you can check by typing “python –version” on Terminal/Command Window. If it returns python with some numbers, then you know Python already was installed. But if it does not, you need install Python.

Install Blender API - Open Terminal/Command Window and type “pip install fake-bpy-module-latest”. This command line will install the latest Blender’s version available using Pip package manager. For more info on visit Fake Blender Github.

Download and install VSCode software - Visual Studio Code.

Install Python extension - open VSCode and go to the extension tab and search for “Python” by Microsoft. The VSCode extensions enhance developer’s experience.

Open Goo folder in VSCode - File > Open Folder (See Git/GitHub section on how to clone Goo on your local machine if you have not done it yet).

Enable and Select Linter - Before you start working on Goo, you need to enable Linter which advise you about the code quality. We are following fake8 style. To enable linter in VSCode, hit ctl + shift + P and type “Python: Enable/Disable Linting”. Click on it and enable it. Now you need to select the code style. Again click ctl + shift + P and type “Python: Select Linter” and then select fake8

Open Terminal - if needed, you can open Terminal in VSCode. Go to Terminal tab and then select New Terminal.

We have already shown how to run Python codes in Blender (see Creating Python file above). In this section, we will show you how to run Python scripts on VSCode written exclusively for Blender.

There are two ways you can develop/execute your Python codes in VSCode.

A) Developing/Executing Python codes in VSCode
Install Blender extenion: same as before open up VSCode and got to extension and search for “Blender Development” by Jacques Lucke

Python file: Create a Python file in VSCode.

Link Blender executable file: Click ctl + shift + p , select Blender: Start, and then select the executable Blender (you can find it in Blender folder). In Mac: Finder > Application > right-click on Blender and choose “Show Package Content” > Contents > MacOS. In PC: find the path where blender.exe exists in Blender folder. Once you link the executable, Blender will launch. Select General to start from scratch.

Run Python script: if you want to run your script, hit ctl + shift + p and select Blender: Run Script. Now, you can see the results in Blender.

B) Developing a Python script in VSCode and executing in Blender
Save changes in VSCode: Save the changes you made in goo.py or any other scripts in VSCode

Create a new script: In Blender, create a new Python script

Reload: To use the attributs/methods of the scripts you created or modified in Blender, you will need to add the following at the top of the script:

from importlib import reload
reload(goo)