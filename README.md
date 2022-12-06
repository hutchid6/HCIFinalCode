# HCIFinalCode
This is the Unity project files for our HCI project

# How to Install
I reccommend using Unity Hub to install the correct version and launch our project. If you don't already have Unity Hub installed, you can install it here: https://unity.com/download <br />
We are using Unity version 2021.3.13f1 <br />
The link to install that version is here: https://unity.com/releases/editor/archive <br />
I reccommend installing the version with the Unity Hub button. When you click the Unity Hub button on the Unity download archive website it should automatically open Unity hub and ask you to install this version. <br />
You are also free to try to use a different version of Unity that you already have installed, but we cannot guarantee that this will work. Versions of Unity that are later than 2021.3.13f1 are more likely to work than ones which are older. <br />
Once you've made sure you have the correct version of Unity installed you can try opening our project with it. <br />
To do this, simply download the zip of this project here: <br />
https://drive.google.com/file/d/1jVhprOModdbhyumiiRBgdstxMjmMAZNL/view?usp=sharing <br />
Then, move it to your desired location and unzip it. Then open Unity Hub, go to projects, and then click Open. This should allow you to navigate to the unzipped folder you've downloaded from here. The file you should select is the one that is the parent of the Assets folder. It should be called HCIProject. You should now be able to open our project and see the implementation. <br />

# How to install for Non-devs
If you'd just like to install the game to play it, you can simply download the build zip, unzip it and play it by launching the application file. The build for Windows is here: <br />
https://drive.google.com/file/d/1mCQwG914EfmVk536OoVRMuT1rOgGG1to/view?usp=sharing

# Overview of the Project
We have a total of 10 scripts in our project. Some are more involved than others and play a much larger role. Some scripts simply handle a small function and are resused many times. We will give a short overview of what each script does and how it connects to the project as a whole. Each script is also commented to help you understand what it does and how it works. <br />

## CameraFollow
This script controls the Main Camera which you see the world through. Every frame it will update the camera's position to be the player's position using a smoothing technique. This script is simply attached to the Main Camera game object itself and only controls the Main Camera. It does get a reference to the player's Transform Component through the inspector though. <br />

## DialogueManager
The dialogue manager is the script which controls the dialogue trees and displays dialogue in the actual game. It uses the Node class to add to its node array and store content that needs to be displayed. The dialogue manager is also referenced by other scripts like the PlayerController in order to see if dialogue is currently playing or not. There is a lot of work done in the inspector for this script, because it basically has a framework for adding all of our dialogue in the game. To see the information in the inspector, navigate to the Dialogue game object in the hierarchy, then find its child DialogueManager. That game object has this DialogueManager script attached as a component.

## Node
This is the class which DialogueManager uses to store all the information required for each piece of dialogue. It includes what text to display, the correct audio clip to play, which nodes it connects to, etc. There are many instances of this class in an array in the DialogueManager.

## PlayerController
This script handles all of the player movement and animations. It also handles one of the largest accessibility features in our game, the pathfinding with directional audio. This script constantly calculates the path to the current objective and will display the arrow and its directional audio according to these calculations. Handling movement and animations is done in the HandleMovement() function. This script is attached to the Player game object and references the DialogueManager to see if it is running or not, and a bunch of different sound objects. We are using a library/package for the A* pathfinding algorithm itself and you can see its use from the Seeker class.

## Door
This is a simple script that we reuse throughout the game in order to change scenes when a player walks into a certain area. It uses a trigger collider attached to the same game object as this script.

## PlayDialogueOnStart
This is another simple script that will ask the DialogueManager to start a certain dialogue node as soon as the scene finishes loading (when a scene starts). We reuse this in every scene where dialogue is the first thing you see. The node that is desired to be started for each instance is determined in the inspector. See the game object PlayDialogueOnStart in the Hierarchy for examples.

## Interactable
This is a script similar to PlayDialogueOnStart except it handles playing the correct dialogue when the player walks up to a character in the game and is prompted to start a dialogue. This handles the dialogue prompt which is controlled using another trigger. It also allows you to assign which dialogue should be started using the inspector like PlayDialogueOnStart. We reuse this script for every NPC in the game. To find it click on any NPC character and find its child named Interactable.

## HelpMenuManager
This script controls the help menu that pops up when the user presses H. It Connects with a few game objects such as the Help Menu itself and the Help Menu Sound that needs to be played to read out the text of the menu. 

## MainMenuManager
This is the script that controls the main menu in the very first scene of the game (the title screen). It has the coroutine for the blinking text, activates the audio for this scene, and allows the user to press enter to start the game.

## PressEscToClose
This final script is very simple and allows the player to close the application when the The End game object is showing. It is connected to this game object so is only active when that game object is active. It should also be noted that pressing escape to exit will only work when playing a built version of the game, and will not work while playing the game in the Unity Editor because it is not an application.



