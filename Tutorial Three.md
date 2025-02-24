# Tutorial on Movement and Jumping
This is a tutorial to teach you how to add movement to an object as well as allow it to jump while moving in a 3-dimensional space. 

## Prerequisites
To follow this tutorial, we will be using the following.
•	Unity
•	Code editing software
I will be using Unity version 2022.3.46f1 which is the standard used version at the University I am studying at as well as the 2022 version of Microsoft Visual Studio Community. 
A basic understanding of how to use these software’s is also needed such as how to create a new project, how to create new scripts as well as adding objects into the project. 

## The Objective
The primary objective of this tutorial is to create a basic tutorial to teach someone how to move an object in a 3-dimensional space as well as for that object to jump. It will be assigned to the standard arrow keys as well as the space bar.

## Setting the Scene
First, you are going to want to create a new project like before and name it what you want it to be called. We will be making this tutorial using a 3D template as we will be programming to move in a 3dimentional space. Once you have selected the right template and named it how you want, select the blue button and “Create Project”.

![image](https://github.com/user-attachments/assets/0c7db2b5-9d25-4817-a832-9561f6e80f61)

Once the scene has loaded, you are going to head to the Hierarchy menu to the right of the screen and right click creating a cube. This is done by going down to 3D Object on the menu and selecting Cube. Name his cube Player. 
Following this, you are going to want to do the same, but this time you are going to want to create a Plane. This is done by right clicking on the Hierarchy menu and going down to Create and selecting Plane. 

![image](https://github.com/user-attachments/assets/a47a2501-2fcc-43c5-b249-97f2761e53a3)

Now, you are going to want to move these objects, so they are not clipping inside each other. Move the Plane down/move the Cube up so there is space between them as seen below. 

![image](https://github.com/user-attachments/assets/cb9e4f6d-59ef-4cc7-8ed7-55fc1ac84434)

Finally, you are going to want to move and position the camera in the way you want it to be positioned, that captures the ground and the Player object so we can see it move at the very end. 
For the Plane setting, you are going to want to have it identical to mine as seen below.  

![image](https://github.com/user-attachments/assets/8093c4cb-de11-4c65-9818-b0564b9e6fd0)

As for the Player object settings, I am using a cube as my base object for the Player like my first tutorial. If you are using a different object your settings menu may look different and may make it harder to follow along with this tutorial. If you have used a cube, it should look like the settings seen below. 
In the Box Collider, it is important to have “Is Trigger” deselected along side “Provides Contacts” as these will make the object phase through the Plane below. 
You are going to want to select “Add Component” at the very bottom of the Inspector menu and type in “Character Controller” and add it to the cube. This will add the second green component seen in the screenshot below. I have not edited the settings on this component so they should be identical. 
The Boc Collider gives the cube the collider shape of a cube which allows it to give it a presence in the scene that can be used to prevent things from phasing through it like a ghost or be used to act as a hit box where damage can be taken. 
There are different shapes of colliders you can add in Unity, but the Box Collider is the most accurate one we need for this tutorial. It’s best to match it to the shape of the object for accuracy’s sake. You can resize it if you would like to. 
The Character Controller component will allow us to control the object named Player as it adds the basic logic of commands such as left, right, up and down. This makes it easier than creating separate inputs in the script writing specifying each direction with added force. 

![image](https://github.com/user-attachments/assets/00b7dc3c-e4f9-43e1-9bf0-75aaa4e47823)

You can see the script which is titled “Movement” at the bottom, this will be added after the next section so do not worry. 

## The Script
Under the scene editor, where is a menu which reads Assets. Here, right click and go down to create and then select “C# Script.” Name it “Movement” though if you name it something else, remember what it is named as you need to recall when writing the script. Then open it. 

![image](https://github.com/user-attachments/assets/3b575d02-d3c1-4896-8048-afd54fec4b19)

You will be greeted with a blank Unity template within Visual Studio, the program we are using. I have gone through what each of these template lines mean in my first Tutorial, so I will not be going through them again here as it does not change. 

![image](https://github.com/user-attachments/assets/48a03984-0a14-4fdc-8dbe-5984598d9e5d)

To start, the public class needs to be correct and should say “public class Movement : MonoBehavior.” Next, we will write some private and public statements to make the script work later.

![image](https://github.com/user-attachments/assets/5a3aa000-3497-4f61-aa09-2a97584db21b)

The difference between private and public classes is whether they can be seen and accessed/edited in Unity or if they can only be seen and edited in the script itself. For example, speed and jump are all public but gravity is not. 
When looking in Unity at the script component on the Player, we can see the first two which can be edited in the software, but not the gravity. If you were to change the private to public for gravity, then it can be seen and edited in the Unity Engine. 

![image](https://github.com/user-attachments/assets/e5aaa410-ef79-40b5-b37f-beffdafae819)
![image](https://github.com/user-attachments/assets/074493be-4f3b-4787-ba53-12a8ca0a93d3)

The meaning of “float” is to represent numbers what have decimal points in them such as 3.2, 5.8 and 45.2 as random examples. This allows us to set the values of the three commands to any number, not just whole numbers but decimal numbers too for more precise variations. 
speed is how fast the Player can move in the scene.
jumpHieght is how high the Player is allowed to go when jumping.
gravity affects the Player movement in the air when ascending in a jump but also descending to finish a jump. This can be set to make it feel like the Player is jumping on the moon if desired.   
All the numbers below are ending in a lowercase “f” which signifies “float” and tells the logic of the program that the number is linked to the “float” in the same line in the script. 

![image](https://github.com/user-attachments/assets/35b6ca04-73f2-470d-856d-1a01ef639426)

Just before these three lines are another three private lines. 

The term “CharacterController” is what tells the program that the Player can move around using key commands on a keyboard which is a better way to implement movement than using “Force” and “ForceMode” as seen in my first tutorial. 
“Vector3” has been used before in the other tutorials and represents the 3-dimentional template and scene we are using. 3 as in the X, Y and Z axis. 
The term “bool” stands for Boolean which is a binary value of either true or false.

![image](https://github.com/user-attachments/assets/016616e6-05c4-4425-8cbd-e026e9b30ef3)

Under “private void Start()” we will be adding the following text seen in the screen shot below. This tells the program to instantly allow for the inputs of the keyboard to move the character via the Character Controller component on the Player object in Unity. 
GetComponent is the command that searched and finds the component added to the object with the component in question being “CharacterController” which we have added in the “Setting the Stage” part of this tutorial. 

![image](https://github.com/user-attachments/assets/b20bd301-565f-44b0-83f0-420510790f81)

Under “private void Update()” we will be adding an “if” statement as seen below. What this statement does is check if the Player is grounded which is defined as not moving on the Y axis – the axis that would move the player vertically. 
If the player is not moving on the Y axis (represented by velocity.y < 0) and there is no input in the “controller” for the Player to be recognized as not moving on the Y Axis (making it considered grounded) then there will be no movement on that axis as represented by the “= 0f;”

![image](https://github.com/user-attachments/assets/6dd5e810-573c-4fc2-8a6b-fb60d5b99220)

Next, we will be coding more of the movement by using a couple of “float” statements followed by “forwardMovement” and “sideMovement” which are terms which will be redefined later in the script. In short, they affect the direction of movement. 
“Input” refers to the means of interaction with the game based on the specified input commands programmed. If the Spacebar opens the box, the Spacebar is the input which affects the game. 
“GetAxis” simply tells the program what axis and direction the Player will be moving in which is also expanded upon with “Vertical” and Horizontal” in the brackets. 
The last line is also defined later in the script, but all it says in the command “Move” affects the forwardMovement as well as the sideMovement. 

![image](https://github.com/user-attachments/assets/892ef9af-f08e-482b-86a4-ce3fc7290a5b)

The following “if” statement is what controls the jumping in the game. 
The first line suggests that if the Player is in the “grounded” state, which means it is not moving on the Y axis and there is an input of the Spacebar, then the Player will jump in the game. 
The “&&” is a logic and operator command which means it will search the program and script with a sense of logic which can be interpreted in the “if” statement under “private void Update()” in regards to if the player is considered “playerGrounded”, then it will allow for the next component in the current “if” statement to work. 
The next component here would be the recognition of an “Input” of a key which has been set to the Spacebar. Together this will allow for movement on the Y Axis. 
However, this movement is determined by the following line. This line does some mathematics and therefore makes everything thus far even more confusing. But in short, the “velocity” which is movement in 3-dimentions, specified on the Y Axis with the “.y” at the end, is based on the “jump” and “gravity” along with the middle value.  

![image](https://github.com/user-attachments/assets/03255ea8-aec0-4f51-84ce-f2f96f6c4699)

The next few lines also look confusing, and I think it still is. The value of “gravity” and the Time which would often be defined by the frame rate would be added and applied to “velocity.y” which means based on the passing of time, based on the frame rate and the “gravity,” which I the movement of the Y Axis is put to gather to determine the speed and movement of the Player when moving on the Y Axis. 
This would be calculated and applied when the “controller” input is activated which is done when affecting the “Move” function. This is done via the “CharacterController” component. This movement is now decided on “velocity” in relation to “Time.”

![image](https://github.com/user-attachments/assets/3bea09b8-f46c-49e8-996b-c62f3944997e)

This is the whole command for the jumping mechanic in the game. 

![image](https://github.com/user-attachments/assets/3c235b34-4861-4825-b8cf-c23921e41830)

The final section of the script refers to a section in the middle, before we wrote the jumping function. This section is what defines the command of “Move” in relation to the “GetAxis” commands. 

![image](https://github.com/user-attachments/assets/49028276-2a52-436d-b8a1-9f2444133db6)

To start, “private void Move(float forwardMovement, float sideMovement) is hidden from being able to be seen in the Unity Engine and is what the following lines of code refers to. It refers to the third line of code seen below which was in the middle of the script overall. 

![image](https://github.com/user-attachments/assets/ad5107be-a3e7-4ab7-b57e-7bfa601ececa)

To simplify these 4 lines of code, all it is doing is redefining the terminology seen in the lines of code in the screen shot above to eventually be represented in one command – “Move.”
What it is doing is changing the terms “forwardMovement” and sideMovement” to be known as “moveForward” and “moveSide” respectfully. 
Then both new terms are simplified into a single term, “totalMovement.”
Finally, “totalMovement” is simplified and defined based on the “speed” as the command of “Move.” 
“Move” not only affects the movement on the axis’ but also takes into consideration of the speed of the Players movement. 

![image](https://github.com/user-attachments/assets/1fa49f26-69dd-49d5-a31d-a1f5c84ee351)

This is shown in the final line of the script seen below. The “controller” affects the “Move” function, which allows the Player to move on all three Axis’ within the game based on the passage of time within the program which normally is based on the frame rate. 

![image](https://github.com/user-attachments/assets/fbc99ae6-0761-44b5-b3bd-66b8e191c1f1)

The final script should look like this as seen below.

![image](https://github.com/user-attachments/assets/3aca76c1-75cf-4418-823f-222ad10095e0)

Moving on, we will save the script and apply it to the Player object in the scene which was made at the beginning of this tutorial as we were setting the stage.
Simply drag and drop it in the inspector menu and enter the Game mode and test if the cube starts to move AND bounce around. If not, you may want to reevaluate your script. Make sure all opened brackets have a closed counterpart. Make sure you have placed all appropriate semicolons and maybe tweak the variables as you may have them too low. 

https://youtu.be/gWEWGIR02jg
