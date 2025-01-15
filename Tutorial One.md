# Tutorial on Scripting Pick-Ups

In this tutorial, we will look at how to write a script to apply collision onto objects in a scene in order to pick the items up as well as count the collected objects.

## Prerequisites

In order to follow this tutorial, the following must be available to use.

- Unity
- Code editing software

For this tutorial, I will be using Unity version 2022.3.46f1 which is the standard used version at the University I am studying at as well as the 2022 version of Microsoft Visual Studio Community.
A basic understanding of how to use these software’s is also needed such as how to create a new project, how to create new scripts as well as adding objects into the project. 
# The Objective
The main objective for this tutorial is teach how to create code to create items in a game setting that can be interacted with and picked-up such as coins and other collectables seen in games. 
This would be an object floating off the ground spinning that would disappear when ran into. This is seen in countless games such as the many Super Mario games with collectable coins and The legend of Zelda series with the Rupees.

## Setting the Stage 
To start, you need to make a new 3D core Unity Project. It is important to select the right template you intend to use. While this Tutorial will be primarily be working as if it is a 2D game as it will only be able to move on a single axis, I will be creating mine using the 3D Template. 
It is important you name your Project the desired title and spelt correctly now as it will not be able to be changed later. Once you’re happy with the title, select the blue button which says “Create Project”
![image](https://github.com/user-attachments/assets/a376d264-6125-4695-a566-bdd850be2184)
Once you are in the scene, the first thing you will want to do is create a Cube object. This is done by right clicking on the Hierarchy menu and selecting 3D Object and then Cube. This Cube will function as our Player in this Tutorial. 
Name this object Player in the Hierarchy menu as this will make it easier to identify what object so what but also to allow the scripts to work with it effectively. This should be done for every object in the scene – especially if you aim to assign a script to it. 
![image](https://github.com/user-attachments/assets/30aa48d2-7167-44bb-be7c-525396b19d37)
![image](https://github.com/user-attachments/assets/f7eb8d0e-8f27-4e76-bd9e-be31546d3e40) 
Next, you will need to add a Rigidbody to it which can be done by doing down to Add Component and typing in the name of this component which can be found at the very bottom of the Inspector menu. 
![image](https://github.com/user-attachments/assets/0ef24aa6-e1e2-4892-8a0c-52f587aa5227)
Next, you will want to do the same. However, this time, you will want to make the cube longer to function as the Platform in the scene. 
Create a cube object and change the X scale to 30 with the position 0, 0, 0 and name it “Platform”. The rotate the platform stretching out in the desired direction and position the cube to sit on the platform so it does not look like it is floating. 
Lower the Platform to make it look like the Cube which will function as out Player is moving atop the Platform and not hovering above it. Make sure to change the name of this object from Cube to Platform. 
![image](https://github.com/user-attachments/assets/f43dc59a-35d3-4ab8-ad7d-dfb72386a315)
Once this has been done, you then need to add a basic cylinder object and change its name to “Coin” for easy recognition and to make your scene as tidy and clear as possible. 
![image](https://github.com/user-attachments/assets/5a089ef1-33a1-4068-867a-6c6790a02999)
Using the Transform menu for the Coin, change the position and rotation of the Coin to not only float above the Platform while also being in the path of the player to interact with the collider, but also rotate it so the face of the coin is facing the camera. This is to make it clear what we are looking at while in Play mode. Below are my specifications for my scene. 
![image](https://github.com/user-attachments/assets/0c149a54-cf3f-482e-8826-8c0c0ad0427b)
However, you must remove the cylinder collider then add a sphere collider with the radius set to 0.5. what this does is add a collider to the object which acts and is shaped as closely to a coin as possible while a cylinder collider does not as much. 
By decreasing the radius, this also allows the collider to fit the size of the Coin so the collision trigger will activate when the player is as close as possible to the Coin without triggering it too soon with a gap between the objects or once the Player starts clipping into the object – both of which would break immersion. 
Tick “Is Trigger” as this will be very important as this will allow the Coin object to be recognised as a trigger for the Player to interact with according to what the programming assigned to it allows. In this tutorial, this would be collecting the coin where the coin will disappear as it will register as being collected with a coin counter to increase by 1.
![image](https://github.com/user-attachments/assets/0c866ac0-c5de-46b3-bcd9-43ca68c84406)
Drag this object into the Assets window. Now the object you have just created named “Coin” has now been made into a Prefab! 
![image](https://github.com/user-attachments/assets/5e7f9e0b-b9a2-4046-ac98-4c62d32ceb62)
Hold CTRL + D to duplicate the object and copy it in the scene with all its settings and assigned script which means the original and duplicates act identically making our job easier. 
![image](https://github.com/user-attachments/assets/8b1a0774-e5a2-4d11-9dca-189af2a894e2)
Next, under the Inspector menu, change the Material assigned to the different objects in the menu to any material you desire. You may need to change some material settings for the material you decide to choose to stand out and work properly. For example, if you choose a metallic material, you may need to increaser the Metallic slider up or down to get the desires Metallic shine. 
It is important to light your scene, so if you do not have one yet, you may need to add a light to illuminate your scene when in the scene editor or while in Play mode. This can be added by right clicking on the Hierarchy menu and selecting lighting then the desired light you wish to add. I have a directional light added. 
![image](https://github.com/user-attachments/assets/48ee1676-d4af-4583-b92f-be931909ca4e)
Lastly, you may also need to manually add a camera which can be done by right clicking the hierarchy menu again and going down to camera. Selecting this will add in a camera into your scene. From here you need to move the camera into position and rotating it on the desired axis to get an angle if desired. 
![image](https://github.com/user-attachments/assets/b25cf9f1-0295-4093-9e11-26ca216196dd)
Finally, the scene is set, and we can move onto Visual Studio and writing the scripts. 

## The Scripts 
Next, we will investigate the process of making the needed programmed scripts we need to give the scene the logic it needs to operate as intended and how to assign them to the objects in the scene. A reminder: we aim to achieve a moving character who collects coins which will be tracked for the coins to disappear when collected. 
Firstly, we need to make our script files in Unity. To do this, you will need to right click in the open Assets menu. Then, in the drop-down menu, select create and then C# Script. 
![image](https://github.com/user-attachments/assets/b9236f41-f985-48dd-8a2b-26b3182e4fb4)
This will create a C# file which you will have to name. to do this, right click on the file and select rename. You need to do this once more as we need two scripts in total. For this tutorial we will be naming them Player and Pickup respectfully. The names of these files are case sensitive so make sure to capitalise them as seen below. 
![image](https://github.com/user-attachments/assets/e5c90196-e32e-48a5-8d05-2fb563e9e18d)
The reason for having two script files is due to the fact we will need to assign the different scripts, which hill hold different logic to different objects, so they all act as intended. 
Fort example, if we give the player script to the coins, the coins will move when the correct input of the keyboard is registered and if we give the Pickup script to the Player object, then it will disappear when the collision is triggered. 
Now, we need to open Visual Studio to start script writing. This can be done by double clicking on the C# file in the asset’s menu. 
You should see a window as seen below. 
![image](https://github.com/user-attachments/assets/8e165ec0-0348-45e1-96e5-bc670e0e0c58)
When opening C# via Unity, Visual Studio will have a template that applies to Unity and video game coding. At the top, you can see it says UnityEngine which tells you what this script template was based on and what it is going to be applied to. Below, it says “public class” which is the name of the script essentially. You can see the name is “Player” which is what I had called the example script. 
![image](https://github.com/user-attachments/assets/773804fb-8499-47b7-afa7-46cecef818a6)
You may notice green text which starts with “//” when you open it up this way. These are notes which do not affect the behaviour written in the script at all and can be written anywhere. However, it is important to start these notes with “//” as not doing so will make the programme think that sentence is supposed to do something but as it is not written to explain behaviour, it will only come up with error messages.
![image](https://github.com/user-attachments/assets/3929793f-8d8c-4a48-a9ae-00bd99fcf28a)
Below in blue reads “void Start()” followed by “void Update()”. What these determine would be how the code in those sections behave and when they would trigger to affect the objects and scene they are linked to. 
For example, “void Start()” affects the start the initial starting point of the scene. However, once this code is run through, effecting the behaviour of the scene at the start, it will not run through anymore. So, what ever they effect will only happen once at the very start. 
When it comes to “void Update()”, anything written under this section of the script behaves differently than as described above. The programme will update every frame and if conditions are met, changes would occur in the playable scene. This would be done to register keyboard inputs which would trigger things like movement or a counter to track collectables such as coins. This means the placement of code is very important. 
Furthermore, you may notice that the capitalisation of the wording is inconsistent. This is due to how the script editor reads the code and how the commands are recognised. This is the same where multiple words are not broken up with a space. It can be confusing but is very important. 
Lastly, every line when coding should end in “;” as this tells the programme the command written has ended and what is written below it is the start of a new command. 
For the first script, we will be working on the Player behaviour. So, if you have not already, open your player script. You will know if it the right script by looking at the public class as seen below. 
![image](https://github.com/user-attachments/assets/ba5cef9d-6c03-4bf6-85eb-2f47cfd1b892)
To start, under “public class” but above the first set of default “//” notes, you are going to want to write the following seen in the image below. It is important to do it on the line below the “{“ too as these brackets layer the logic of game programme code
![image](https://github.com/user-attachments/assets/fe9ec84c-2d7b-4b10-a797-f7f4aded4ff9)
“public Rigidbody body;” effects the Player object as the cube we had made earlier has a Rigidbody component assigned to it. 
“public float force = 0.01f;” also affects the Player in Unity and effects the speed of movement the Player exhibits. I have set the speed to 0.01, but you can change it to any speed you want. However, it is important to remember that what ever the speed of the object is in Visual Studio must also match the speed in Unity. 
This can be done later once the script has been completed. But to show now, once you assign your script to the object in the Inspector menu, locate where it sits in this menu, it will be titles “Plater (Script)” and change the number of Force to the same number as written in the script. Otherwise, issues may arise such as the Player moving too fast or slower then desired. 
![image](https://github.com/user-attachments/assets/a475b7ae-0b65-4413-bb75-6ed031ef2f1e)
On the third line, it reads “int coins;” which is a variable. The type of the variable being signified by “int” which means integer and “coins” which is the variable in question. This line will affect the coin counter. 
The reason these three lines of code are written here and not below either “void Start()” or “void Update()” is because these commands are to be applied throughout regardless of the frame the game sits on. 
Next, we will move down to the “void Start()” section. Here, the commands written will affect the beginning of the scene before the first frame is counted. 
![image](https://github.com/user-attachments/assets/123d543a-eb2d-4b22-982c-c4f39d531dce)
The line; “if (Input.GetKey(KeyCode.Space))” dictates the behaviour of the Player providing certain requirements are met. This is indicated by the “if” at the very beginning. 
“Input” is the type of command that should be followed in the requirements are met. In this case, it would be the input of a key on the keyboard. The activation of this key would be the “if” variable in question. If this key is pressed then do X however, if it has not been pressed then do not do X. 
Getkey indicates the requirement here would be the press of a key on your keyboard. In this case, we want to set the key in question to the spacebar. We would set this using the “KetCode” command which tells the programme what key has been selected with “Space” naming the key – the spacebar. 
The following line; “body.AddForce(Vector3.right * force, ForceMode.Impulse);” is what the “if” statement commands. In this case, when the space bar is pressed, it will affect the Player. “body” is seen at the same place of “force” in Unity and is where the script is assigned to the object in the Inspector menu. 
![image](https://github.com/user-attachments/assets/691f4877-e4fd-45d6-a56a-a48d0b6c0fbe)
“AddForce” tells the body what it needs to do which is move the object, in this case the Player with the desires speed which was stated when assigning the “force” to 0.01. 
The next part of this command; “(Vector3.right * force, ForceMode.Impulse);” tells the object, via the “body” how the “Force” should be applied. 
As we are working in a 3D Project in Unity, the scene and the game being made can move in a 3-Dimentional space. Despite this, we are only going to move in one direction, on one axis, but “Vector3” is the command for something to move in all 3-Dimenations.
Ther direction of this movement is set to “.right*force” which is the direction the Player will move in relation to the speed of the movement. If for what ever reason when moving right is not the right direction you need the Player to move in, changing the direction here is what is needed to correct it. 
“ForceMode.Impulse” is what tells the programme how the movement should behave. While above we dictated how the movement should present as in terms of direction and speed, we need to tell it how it should behave in relation to the input. “ForceMode” tells the programme to take into consideration the behaviour of the “force” with “Impulse” meaning the force applied should consistent.
Lastly for the Player script, we will add code below the green text where it says “// Update is called once per frame” and will change the “public class” from “Update()” to AddCoin()”
![image](https://github.com/user-attachments/assets/ff1f8ee9-02c1-41a1-8906-b229901feea9)
The line; “coins++;” is simple and all it means is to add a single variable to the coin counter.
To affect the Debug.Log, you need to write “Debug.Log” on the next line. The Debug.Log can be seen under the Console below which is next to the Projects menu which allows you to see your Assets menu where your scripts are saved and is below the scene editor.  
![image](https://github.com/user-attachments/assets/ae691fd0-7717-494e-996c-bff083cf7cce)
To add up the coins, the use of “$” in the brackets effects the formatting of the Debug.Log. In this case, it tells the log that any message is a string related to the messages prior. 
Following this, “"Coins collected: {coins}");” what is written in the quotation marks is what the message would say. In this case, it will say “Coins collected:” followed by a number as seen below.
![image](https://github.com/user-attachments/assets/9d6828fc-95b3-46b1-a409-31c434c2023c)
In the curly brackets is “{coins}”” which is where the variable which should be counted and effect the counter in the Debug’Log. In this case, the variable counted would be the Coins when the collision is triggered. So, when one coin is collected it should read “Coins collected: 1” and when two Coins are collected it should read “Coins collected: 2”
This is the end of writing the Player script. It should look like this, seen below. if yours looks different then it is possible you have gone wring somewhere along the way and should keep that in mind as some edits may need to be made to correct the errors. 
![image](https://github.com/user-attachments/assets/6a02c8a8-06c6-44b1-bd1d-0bdadc4499c1)
Lastly, before moving on to the Pickup script, we need to apply this to the Player object in the scene. This is really easy as all we need to do it open Unity and drag the Player script from the assets menu and drag it to the Inspector menu. 
When it is in the menu, make use the speed next to “Force” matches the speed in the script and that the “Body” reads “Player Rigidbody” if not, select the small arrow next to the menu and change it from “None” to “Player”
![image](https://github.com/user-attachments/assets/d3687359-6387-4799-9d9a-1a609efb9527)
And this concludes the Player script. Moving onto the Pickup script, 
Open your second script which should be named Pickup, and you should see a screen just like the one prior.
![image](https://github.com/user-attachments/assets/26a7043b-b8d4-494c-aff6-be386f405b31)
The first thing you are going to want to do is where it says “void Start()” change that to “void OnTriggerEnter(Collider other)”. What this is, is telling the program that this section of the script will work with the collision/trigger mechanic within unity.
![image](https://github.com/user-attachments/assets/ac898176-9d1a-4768-b72b-a69b44c050ff)
Next, write “if (other.TryGetComponent<Player>(out var player))” as seen below. This is an “if” statement which means providing the requirements are met, then the command written in that section would be applied. Otherwise, it would not. 
Here, what the code does is track of the object named “Player” triggers the collision of the “Coin” objects and if the collision is triggered then the logic moves on to the next line of code. 
![image](https://github.com/user-attachments/assets/8f2e6e4b-e924-4e2c-b545-5348fca9e817)
The next line of code reads “player.AddCoin();” which means the Coins will be recognised as being acquired by the Player object which would in tern be added to the coin counter written in the Player script prior. The reason why it reads “player” is because that is the only allowed entity to trigger this function. So if we had an object names “Dog” which this code is not assigned to, then the Dog will not trigger the pickup function we are working on. 
The second line of code, “gameObject.SetActive(false);” affects the object within the scene itself. If the Player triggers the collision, then the Coin object will disappear from the scene so tell the player of the game it has been collected and top prevent it from being collected infinity. 
This command is seen with “SetActive(false)” as false would tell the Coins in the scene, represented by “gameObject” to disappear as it is no longer an active component following the if statement trigger. 
![image](https://github.com/user-attachments/assets/a6aa6cba-a57d-4afe-8807-9a98b3d120ab)
This is it for the Pickup script. It should look something like this. Remember, it is imperative to end the script lines with a semi-colon to tell the logic the specific commands are over. Furthermore, that the placement of the open and close squiggly brackets is as seen below as what is in each bracket is self-contained to specific parts of the script which would trigger in specific order.  
![image](https://github.com/user-attachments/assets/74a29ed8-1166-45b6-9242-1e4b4f785c8f)
All that needs to be done is assign it to the Coins in the scene via the same method shown when assigning the script to the Player. Once that is done, the scene should now work. 
Here is the final video of it working below.
https://youtu.be/1l-8WurIW4A
