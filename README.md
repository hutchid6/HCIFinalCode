# HCIFinalCode
This is the Unity project files for our HCI project

# How to Install
I reccommend using Unity Hub to install the correct version and launch our project. If you don't already have Unity Hub installed, you can install it here: https://unity.com/download <br />
We are using Unity version 2021.3.13f1 <br />
The link to install that version is here: https://unity.com/releases/editor/archive <br />
I reccommend installing the version with the Unity Hub button. When you click the Unity Hub button on the Unity download archive website it should automatically open Unity hub and ask you to install this version. <br />
You are also free to try to use a different version of Unity that you already have installed, but we cannot guarantee that this will work. Versions of Unity that are later than 2021.3.13f1 are more likely to work than ones which are older. <br />
Once you've made sure you have the correct version of Unity installed you can try opening our project with it. <br />
To do this, simply download a zip of this project, unzip it and move it to your desired location. Then open Unity Hub, go to projects, and then click Open. This should allow you to navigate to the unzipped folder you've downloaded from here. The file you should select is the one that is the parent of the Assets folder. It should be called HCIProject. You should now be able to open our project and see the implementation. <br />

# Overview of the Project
We have a total of 10 scripts in our project. Some are more involved than others and play a much larger role. Some scripts simply handle a small function and are resused many times. We will give a short overview of what each script does and how it connects to the project as a whole. Each script is also commented to help you understand what it does and how it works. <br />

## CameraFollow
This script controls the Main Camera which you see the world through. Every frame it will update the camera's position to be the player's position using a smoothing technique. This script is simply attached to the Main Camera game object itself and only controls the Main Camera. It does get a reference to the player's Transform Component through the inspector though. <br />

## DialogueManager



