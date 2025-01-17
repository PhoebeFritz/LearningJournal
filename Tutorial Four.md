# Tutorial on Locking the Camera on the Player and Following
This is a tutorial to teach you how to script a camera to lock onto the player and follow them wherever every they go on the screen. 

## Prerequisites
To follow this tutorial, we will be using the following.
•	Unity
•	Code editing software
I will be using Unity version 2022.3.46f1 which is the standard used version at the University I am studying at as well as the 2022 version of Microsoft Visual Studio Community. 
A basic understanding of how to use these software’s is also needed such as how to create a new project, how to create new scripts as well as adding objects into the project. 

## The Objective
The main goal of this tutorial is to be able to write a script that tells the camera to change its position in relation to the player and keep the Player in its sights, following the Player wherever they go on the screen. 

## Setting the Scene
To start this tutorial, you are going to want to create a new Project wit a 3D Template and name the project however you want. For this tutorial, I will name mine Tutorial 4. Once done, select the blue button to create the project. 

![image](https://github.com/user-attachments/assets/6b6aab9a-1bb4-4eb1-a270-e452dc81f344)

First, you are going to want to create a Plane which will function as the floor for this scene. This can be done by right clicking in the Hierarchy menu and going down to 3D Object and selecting Plane. 

![image](https://github.com/user-attachments/assets/87818ff7-249e-4654-b160-31210099b204)

Next, you are going to want to spawn in a cube which will function as out Player. This is done via the same method mentioned prior where you will select cube rather than Plane. Name this Cube Player. 

![image](https://github.com/user-attachments/assets/b7d3cd3c-3e0a-4529-9f84-9c47459fe955)

Next, you are going to want to import the Movement script we had create prior in the last tutorial (tutorial 3) and import it into the asset’s menu below the scene editor below. You can do this by finding the script in your documents and dragging it into the asset’s menu, 
If you cannot find it, an easy way to find it is to open your last tutorial in Unity, then open the script via the asset’s menu in that tutorial. Next copy it and open a new script in the new tutorial (tutorial 4) and paste it in Visual Studio. Alternatively, you can save the script via Visual Studio somewhere you can find it easily like the desktop and drag and drop it in the asset’s menu in the fourth tutorial. 
If you have not done tutorial 3 and therefore do not have this script, then all you will need to do it right click the assets menu below and create a C# script by right clicking the menu then selecting “Create” then C# Script”. In the new Visual Studio script, copy what you see below. make sure to close all brackets and use semi-colons in the right places. 

![image](https://github.com/user-attachments/assets/35f36015-8f73-4aed-a9d4-a1f4b6d15f67)

This is important to include as we will need a character that will move around in the scene and as we have made a script for it then we may as well reuse this one here. However, if you do not care to do all then or have the time, you could try and use the programming seen below which is much simpler. The downside, it is works differently than the script seen above and can only more in one direction nor can it jump. I recommend the script above as I will be using that one. 

![image](https://github.com/user-attachments/assets/812aa7c5-e795-4de1-8a8f-dff8faaf49e8)

Next you are going to want to assign it to the Cube named Player which is easily done. In Unity, drag the script when the Player is selected and drag and drop it where is saying “Add Component” in the Inspector menu. The menu should look like this below. 

![image](https://github.com/user-attachments/assets/161b9156-f14e-4aba-aeb1-4278b63563ab)

Quickly test out the movement to see if it works. If not, then something went wrong. If you are getting errors, the issue is the programming in the script and the errors, when double clicked, will take you to where the issue is and explains to you what the issue is as well. Fix these errors and try again. 

## The Script
Now, we are going to make a new script which will affect the Main Camera in the scene, the focus of this tutorial. Start by right clicking ion the Assets menu and down to “Create” and then select “C# Script.” This should create a new Visual Studio script to start programming in. 

![image](https://github.com/user-attachments/assets/40b8caa2-9b48-42a0-9ad9-9c5e3f01d5a5)

Name your script how ever you want, but I will be naming mine Viewer as this will affect the view of the Player and how the game will be framed. 
When you open the script, start typing in the code as seen below. We are going to want to have some standard public and private statements as seen below.
The line “public Transform target” is what allows for the manipulation of the position of the subject in relation to the target, which is what is being tracked. 
The line, “public Vector3 offset;” allows us to set the position of the camera in relation to the target it will be following – the Player in our case. We have set this public as this will allow us to manipulate this setting in the Unity engine. 
The line “public float speed” is what gives the camera the speed to keep up with the cube. This is set to 10 to make it fast. 
The line “public float smoothTime” is what affects the camera spinning around to look at the target which is set to “0.1f” to keep up with the Player and have no lag. 

![image](https://github.com/user-attachments/assets/d69a06ed-7cef-4af1-8bf2-426e9328a2bd)

“Vector3 targetPosition = target.position + offset;” is the line which tells the camera to position itself in a 3-dimentional space in relation to  the position of the target set, the Player in our case, with the difference between the two positions kept in mind an kept. 
This is continued down below as “transform.position is defined as taking into consideration some ofther factors together. Which included Vector3 to move in 3-dimentions with the speed of movement as well as the spin of the camera in mind with the “velocity” and “smoothTime” included at the end. 
The term “red” “ref” means in reference to something and in this case, it is in reference to the velocity, or speed of the camera. 
“SmoothDamp” is included to give different effect if desired where it takes time for one value to meet another in terms of time. So, if I move the target position and the camera is set to meet it with its own offset in mind, the camera will move to meet this new position change, but will take time as it will move to that new position. 

![image](https://github.com/user-attachments/assets/94c034dd-b2ec-45f4-9d14-7f7b7c3ccc2a)

This is what the final script should look like.

![image](https://github.com/user-attachments/assets/176e49ec-09d1-46f7-80c9-dea81e1f9962)

Now the script is done, we will add this to the scene and see if it works. To do this, like the Movement script prior in this tutorial, drag the Viewer script and drop it on the camera to assign it. 
When you assign it, you need to set the Target which can be done by selecting the small arrow and selecting the Player in the list. This will allow the camera to target the Player in the scene and follow it as it moves. 

![image](https://github.com/user-attachments/assets/50eb85ba-c05c-4800-acff-ff75d98efdce)

Make sure to set the Speed and Smooth Time to what was set in the script in Visual Studio as if they are not the same then the change in Unity will not take effect. 
As for the Offset, you are going to want to play around with this to make sure the camera is framing the Player in the way you want or need it to. Make sure to enter Game mode to see if it is correct as if you set the co-ordinates wrong the camera will move in Game mode from the starting position to meet the Offset position. 
An example of this would be if the camera is set in the positive axis, but for some reason the Offset is set in the negative or vice versa. 
Once this is done go into Game mode and see if the script works. If so, congratulations you have a camera that follows the Player as they move around in a 3-dimentional space!

https://youtu.be/92QV5Teq3PE
