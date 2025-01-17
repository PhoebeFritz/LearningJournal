# Tutorial on Creating a Play Button
In this tutorial we will be looking at how to create a play button where you have a button to start the game and load the first scene.

## Prerequisites 
To follow this tutorial, we will be using the following.
•	Unity
•	Code editing software
I will be using Unity version 2022.3.46f1 which is the standard used version at the University I am studying at as well as the 2022 version of Microsoft Visual Studio Community. 
A basic understanding of how to use these software’s is also needed such as how to create a new project, how to create new scripts as well as adding objects into the project. 

## The Objective
The main objective of this tutorial is to create a menu where the player of the game has an option to start playing the game and load the scene. This will be in the form of a button which would function in the expected capacity.

## The Start
To start this tutorial, all you need to do is create a new scene for this to be created in. To do so, open Unity as usual and when the Unity Huib menu is loaded, select “New Project” which is the blue button to the right of the screen. 

![image](https://github.com/user-attachments/assets/670dd1f8-e4cb-43c3-b66d-4eb1fad98e27)

Name the project how you want as this cannot be changed later. I will be naming it “Tutorial 2.” I will be creating this using a 3D Template as before, but the tutorial I will be showing can be used using a 2D Template as well. When you are happy, select “Create Project” in blue at the bottom right of the screen. 

![image](https://github.com/user-attachments/assets/1e609e81-2ed9-42e5-81dc-606f920ca603)

Once the project has loaded and opened, in the Hierarchy menu at the left side of the screen to the scene editor, Right click and scroll down the menu until you see “UI”. Open that sub-menu and select “Button – TextMeshPro.” This will create the tools we will be assigning the scripts to for the menu to work. 

![image](https://github.com/user-attachments/assets/4477b83a-52d2-47bc-a3f2-b0b504a533f9)

This will create a massive white, semi-transparent plane. In the Hierarchy menu, it is listed under “Canvas” and named “Button” which is what we want. Around it, there is a transparent square which is the canvas itself. 

![image](https://github.com/user-attachments/assets/af6bb4ed-ff98-4d74-8e0f-a5b6d3ac115c)

If you were to go into the camera, the diameter of the canvas is the representative of the frame of the camera and the white button is where the button sits when in the menu itself. So, you need to move the white button to be in the position you want it to be in and enter Game mode to make sure it is where you want it to be. 

![image](https://github.com/user-attachments/assets/62f99e6c-5266-4d86-8abf-5ff6924283a8)

## The Script
To create a new script, right click in the Assets menu and under “Create”, select “C# Script. You can name it however you want; however, I will be naming mine “Play Menu” 

![image](https://github.com/user-attachments/assets/afb237a3-31ce-4f07-b7c4-be97cb0bcf0f)

Once it has opened in Visual Studio, it should look like this below. A blank template for Unity programming. The explanation of what all of the template means was explained in my first tutorial, so refer to that if need be. 

![image](https://github.com/user-attachments/assets/93c34c6f-05ca-4a43-a076-1f71db0efe52)

To start, you can delete the whole section of “void Update()” up until the second to last close bracket “}” leaving the very last one. The green text can go as well. So, all that is left is the “void Start()” section as seen below. 

![image](https://github.com/user-attachments/assets/5a088fe8-ac08-43b1-83a3-7cc672d14a96)

However, we will be editing this section to fit our needs. Where it says “void Start()”, we want it to read “public void PlayGame()” This tells the logic of the program that the script we are writing is to function in a way to effect whether the game should start or close which is a large function that is not within the game, but starting the game itself. 

![image](https://github.com/user-attachments/assets/5e846e90-b90d-4741-939e-fd9ea615a2ce)

Lastly, the final line you need to write is “SceneManager.LoadSceneAsync("Game");” What this does is allows for text to appear on the button itself which should aim in telling the player of the game what the button does. 
This effects the scene itself as represented by the “SceneManager” specifically with loading the scene in once the button has been pressed as represented with “LoadSceneAsync”

![image](https://github.com/user-attachments/assets/dab36d4b-14e1-4cde-909b-aeea5b49bc64)

And that is it. Pretty simple. Your script should look like the one below. Do not forget to end lines with a semi-colon and make sure the brackets are opened and closed each as seen below. 

![image](https://github.com/user-attachments/assets/269161cb-f351-4340-825b-4891693d4d62)

To add it to the scene, we need to apply it to the “Main Camera” which is simple. We need to drag the script from the asset’s menu over to the Inspector menu as add it.

![image](https://github.com/user-attachments/assets/c5fbe900-dbea-4ba0-a397-36bfc4eea025)

Once that is done, we will change the text that appears on the button to say, “Play Game” which can be done by opening the menu fully the selecting the third option. Then on the Inspector menu to the left of their screen, we will change the name at the top to identify it in the Hierarchy, but we need to ass “Play Game” in the box that says, “Text Input.” The button should now say “Play Game.”

![image](https://github.com/user-attachments/assets/31c0bf95-8073-4de8-a4cb-54650fca5fb9)
![image](https://github.com/user-attachments/assets/e66bca97-dd6d-4b99-8e69-aea00bcc80ba)

Next we will make a new scene to test out this menu. To do so, open the Scenes folder in the Assets menu below the scene editor and right click and select “Create” then go down to “Scene.”

![image](https://github.com/user-attachments/assets/3f87fba5-f184-44c6-9d2c-bf2c093ce09c)

Name this scene “Game” so we know what scene what is. It is important that what you name this scene is the same as what is in the script as seen below. If you named yours differently, then match them up before proceeding. 

![image](https://github.com/user-attachments/assets/cf06ba03-351c-47ee-9b3a-2e2d1346be71)

We will add a plane in the Game scene so we know that there is something that will change in the Game mode in Unity which we can see with the plane color changing the appearance of the scene. 
This is done by right clicking in the Hierarchy and doing down to UI and then Panel. The panel will sit in the parameters of the “Canvas” for you so you do not need to edit it unless you need to or want to. 

![image](https://github.com/user-attachments/assets/a810b35c-048d-49b5-91b3-25783de9c235)

Next, go into file and down to “Build Settings” and you should see a menu open. With two scenes down in the Assets menu, you need to select “Add Open Scenes” and the “Game” scene should be added as seen below.  

![image](https://github.com/user-attachments/assets/489d2111-1824-4e5e-9fad-abd8afa8e9e0)

The number to the side of the scenes could be used alternatively to the name of them in the script. Where it says ““SceneManager.LoadSceneAsync("Game");”, you can change the word “Game” to be the number 1 which is a short cut to “Scenes/Game” as seen in the “Build Settings” above. We will keep it as “Game” for now regardless, but the option is there for simplicity’s sake.

Next, we will go onto the “Button” in the Hierarchy menu under “Canvas” and look in the Inspector menu to the left. There should be a section that reads “On Click” where we will select the “+” at the bottom of it. 
We will add the “Main Camera” in the drop-down section on the bottom row and “PlayMenu.PlayGame” at the top. 

![image](https://github.com/user-attachments/assets/8a50b959-01de-4748-8d4a-eba121a834b4)

![image](https://github.com/user-attachments/assets/9c096984-1b86-48d1-a287-440e319e25c0)

With this done, the program should now work. Go into the game mode when in the first scene with the button on and see if it works. If not, you must have gone wrong somewhere along the way. 

https://youtu.be/h5BMUuZpUaU
