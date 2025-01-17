# Prototype

For the Prototype, I decided to make a 2-dimentional platformer using the Visual Studio scripts I had made for the 4 prior tutorials.
# Video of my Prototype

https://youtu.be/fPaH8cG34W4

# The Source Files

[1.1 Final Prototype Source Files (2).zip](https://github.com/user-attachments/files/18451045/1.1.Final.Prototype.Source.Files.2.zip)

To access the final Prototype with all the source files, please download this link and then unzip the folder. From here, go onto Unity Hub and where you can make a new project, select add and select "Add project from disk." This should be the proper way to open the Protoype on your end. 

# Write-Up
The VLE does not mention anything regarding talking about the making of the Prototype, but to keep all grounds covers, I will be writing about it just in case. I will be writing it not like the prior tutorials, explaining to someone how to do something but rather as evidential documentation to show the process of making it. 

To start, I opened a new project using a 3-dimentional template and started to test if my plan would work. This was to apply the Movement script, written to work within a 3-dimensional space, would work in a 2-dimentional scene. 

To my grateful surprise, it did. However, the controls still worked in a 3-dimentional scene. The solution here was to go into the script and edit it slightly to prevent the assigned object from falling off when the up or down arrow would be pressed. 

This was super easy as all I had to do was change “Vector3” to “Vector2” as the numbers indicated the dimensions of available movement. Now designed to work in 2-dimentions, the Movement script had been completed for the Prototype. 

I spun the cube around though so only the up and down arrows worked until I figured this out and rotated back to the original position. I spent a while spinning everything around like the camera and floor, but the issue was the Player cube. 

I did not have to change anything in the Viewer script thankfully. 

I did start this off trying to make this in the 2D Template and the edits I made in the Movement script, changing “Vector2” to “Vector2” worked to my surprise. 

However, the issue arose when I tried to use the Viewer script in this template. The camera would not move, even when I added the component that made the camera follow the target both in view and position. No matter what I did I could not seem to get it to work. 

In the end, I decided to make it with the 3D Template and as stated prior, changed the Vector number and the desired effect is present, so this is what I am going with in the end.

I created more cubes which I would manipulate the size and shape of and create obstacles in the way of the Player collecting coins. I would duplicate these and spread them out and stack them. 

Next, I created the coins by rotating and reshaping a cylinder which I would assign the Coin script to. I would duplicate this coin and create more of these around the simple platform I had created as collectables. 

I did not have to change the Coin script in any way for the coins. However, I did have to add some parts to the Movement script which would recognize the coin by the Player as well as the function to collect them, adding to the coin collection counter and make the coins on the platform disappear. 

Lastly, I implemented the Play Button mechanic I had created which turned out to be the hardest part of the Prototype. The issue I had was implementing the “On Click” command at the very end for the button to change from the Play Button scene to the Platform scene.

The issue I had here was once I selected the Main Camera in the Object menu under Runtime, I needed to select the No Function bx and go down the menu and open Play Menu, then Play Game () which I completely forgot I needed to do from when I made this tutorial last time. 

The most fun part of the Prototype was making the platform with the 3D Objects. For some reason this was calming for me, but I also enjoyed taking my time and seeing what I could create in terms of a simple platform level.
Surprisingly, I enjoyed this module a lot which was not something I would have thought would be the case. Seeing some confusing script turn into something functional was exciting for me and something I felt invested in when making it. 
Playing the final Prototype was really fun and I went through it a few times as I enjoyed it so much :)
