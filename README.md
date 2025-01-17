# LearningJournal
This is my Learning Journal for Programming at University. 

## 
# Week 1
I learnt about Scripting API Unity Documentation whch explain what each command does to aid in independant programming. Hopefully :)

# Week 2
Anatomy of Scripting on Moodle VLE breaksdown the elements of script lines to aid in my understanding of what everything means. 

##
# 05/11/2024
I started to work on my first tutorial properly after a couple of weeks progcrastination and focusing on other modules. This was difficult as not only was coding new to me but i also felt being on the fifth week of the semester, i felt i was unbelievable behind and needed to rush to catch up. I learnt that API Dictionary hdoes not have all termonology in as some of it depends on C# and the terminology used specific with the program. I also found out about DotNet website to help find these programe specific terms wth help from Paul, our teacher for this module. I started by looking at the tutorials Paul had made and used it as a reference for formating my tutorials, but also to breakdown the coding he had done as a basis of looking at what each word and term meant in C# to help my learning and understanding of the code. 

# 06/11/2024
I went to the Games Lab woth Olivia and Isaac to work on my tutorials with that aim to help focus while working which would be difficult at home on our PC's and Laptops. I continued to breakdown all of Pauls code in order to understand it. 

# 11/01/2025
When trying to work on my first tutorial on my home PC, one issue I had was that Player was recognised as a Class as well as being used as a Type which meant I could not use the scripts in Play mode in Unity. This was due to some of the "player" types being capitalised which created confusion as the Class was named "Player" which meant I needed to lowercase the Capitalised types. 

Another issue I had with the script was this line; Player player = other.GetComponent<Player>();. For some reason the programe did not like it and I do not know why specifically. However, Visual Studio recommended changing the line to; if (other.TryGetComponent<Player>(out var player)) which seemed to work.

The next issue I faced was the Player would collide with the first coin then float up into space like an astronaught on the moon. The issue was, I did not enable "Is Trigger" under the Capsule Collider in the Inspector menu for the Coin Objects. I duplicated the first Coin and the Inspector settings and assigned script very easily, this was done by holding CTRL + D then moving the new Coin to the side and repeated this until the platfoirm was filled. The settings and assigned script copied over too. 

When trying to play the scene, the camera was facing the back end of the Player cube which meant I needed to rotated the platform and coins and then move the camera out to get a view of the whole scene which I did noit know I could do with the camera. Using the scene editor and moving the objects and in the scene along with some of the controls were easy to pickup as they are similat to Maya's user interface and keyboard controls.

I wanted the Player to not float above the platform but look like it is gliding along it. I tried to get this with the Gravity setting being enbaled in Rigidbody but this would cause the cube to roll which I did not want as it would fall sideways off the Platform. After a while, I deselected the Gravity setting and just moved the Cuve down to make it lok like it is gliding atop the Platform. 

I would add the code which would allow me to keep track of the Coins collected.

After moving the Player down, I tried to add colour to the scene objects. However, I could not and I believe it is due to me not having certain downloadable content installed which would allow me to change the colour of the objects. This is disapointing as leaving the default Materials on makes the final piece look boring with little effort put into it. 

# 15/01/2025
I have finished my first tutorial finally. I have been having issues with motivation and my mental health hence why it has taken so long to get this all done. I have a couple of days to get 3 more done and the prototype... I have made a plan that every tutorial I will be making will all be made into one which will function as my Protoype. The reasoning for this is to save time to get this work done before the final deadline. I also have planned what each tutorial will be and how each one can work together to make a Prototype where I will make a rudementary game showcasing the programming skills I am learning. 

One thing I noticed was explaining how the tutorial is supposed to go to someone who has no idea how to programme has helped me understand what the programming terms mean within Visual Studio somewhat which was very suprising. I think this stems from explaining what each line does and using some logic t deduce what he terms mean using the hints and intuition based on what key words are used. However, I am aware how limited this understanding would be. 

For the second tutorial, I chose to make a play button which would open the game based on the click of the mouse. I chose this as often this is a fundemnetal aspect of video games and would be useful for other button prompts in the future if needed. I did not know how easy making a button was as a start menu of sorts. I am unsure if the method I chose to use for the button would work for other UI button controls for in-game menus and such. 

Creating the buton as well as changing what the button says as well as switching it to a different scene was all new to me. I had to download some files for the Text Mesh Pro to work with the button as the text would not show at all otherwise. I did not real;ise this initially as I had ignored the text boxes that popped up at the bottom of the screen initially. However, I would soon read them and realise what the issue was. 

I chose to add it to the camera as this would be a scene that would only appear once and I wanted it to be gone once the buton was pressed. I thought if i made it all on one scene, a dissapearing button n the same scene as the game would create a lot of confusion. Putting the button on one scene and then the second scene would be the scene with the game would create less confusion or hassel when paired with more code. 

I had an issue where when I would spawn in a cube, the shape would not appear for some reason and I have no idea why this was. I did not get round to findin the source of the issue unfortunatly, but I hope to god this issue does not persist when moving forward. 

I had issue using the Build Settings initially as I got confused how to add a second scene to it. I tried opening my other projects and opening it that way which did not work. I tried to drag and drop these other projects into the Assets menu which also did not work. Eventually I realised all I needed to do was right click the menu and create a new scene. This would solve the issue and to be hinest, I am somewhat ashamed I did not think of this sooner. 

Adding the button script to the camera was also something I did not think I needed to do, but I after making this tutorial, I know the On Cliuck menu needed the Main Camera added to it for the button to activate when click on by the mouse. This took me a while to figure out as the button wopuld not work. The solution was to select the + button underneath the sub menu to add what I needed. 

# 16/01/2025
The third tutorial was the hardest, however looking at my first totrial, I started by using the "Force" and "ForceMode" commands which allowed the assigned Cube named Player to move in one direction when the Spacebar was held continuously. I copied this several times and changed the direction of the movement linked to different arrow keys. While this worked in movinf the cube, the issue was they cube kepy moving after the key had been pressed as it would slowely slowdown. In other words it was mivinf like it was on ice. 

The solution to this had me searching up differnt tihngs I could do differently which included the "ForceMode" commands and changing it to copmmands such as "forwardMovement" and "sideMovement" which I would Google how to simplify into a single command to execute. This was really confusing and took me a while to do. This method also taught me about the Character Controller component which I could use the prior code on. This made the character controls much more smoother and less like it was skating on ice. 

The rest of the script took just as long as I had no idea how the rest was supposed to me formatted and looking at commands from other scripts my teacher Paul had shown us as well as using the ADP dictionary of Unity/Visual Studio sript writing and asking Google what to write to get the outcomes I desired. I somehow managed to get it to work. The downside is some aspects I do not understand even with the extensive Googling. 

For example, I have used the Asteriks (*) being used prior which the "deltaTime" commands, yet I do not actually know what the Asteriks (*) actually does. My understanding is it multiples things similar to how it is used as a keyboard shortcut for calculators and such, but desite Googling I could not get an answer that made sense so I cannot say for sure. 

I also had to turn "IsTrigger" off for both objects in the scene to prevent them from phasing though eachother which was a massive issue that took forever to solve. Alongside this, removing RigidBody also helped in the cube working the way I wanted it too as I think this was the mian cuase for the phasing and the collapsing floor issues. This took me 4 hours to solve... thanks Google :)

This tutorial took the longest out of them all and I am so happy it is over. Getting the movement to work normally and not on ice paired with getting the jump to weork when the SPacebar would be pressed was an issue when using "ForceMode" as sometimes it would not recognise the input and getting the cube to move ON the Plane below and not phasse though or cause the Plane to collapse under the weight of the Cube also took way too much time to solve.  

Today, I worked on my final tutorial and I chose to work on making a script to make the camera follow the Player as they moved. This tutorial was rather easy in my opinion and took no time at all making and applying it to the scene and have very minimal issues when makeing it bar the positioning of the camera in relation to the Player with the Offset settings as well as the controls reversing as I would accidently set the positioning reversed where I would set them in the positive axis when they should be in the negative and viceversa. 

I learned new things such as what SmoothDamp meant as well as how to set a target using a script. Furthermore, while not in the tutorial due to it making it null and void, I learnt that there is a component that you can assign the camera that will allow it to track your desired target for you without needing to write a script at all. Furthermore, I also learnt that of you parent child link the camera to an object with the object being the parent, then the camera will move along side the object - in this case the Player with the fixed Offset settings in mind. I did not know this but chose not to include it when I did as it would defeat the purpose of the script. 

Some of the easiness of this tutorial case from reusing the Movement script from tutorial 3 for the basic movements. With my understandng of most of the terms and some reseacrh online, the script came together rather well. Though I did set the velocity to public when experimenting and unltimatly got confused when testing things out while messing with the script and public settings as the velocity numbers would move rapidsly for me into very high numbers and would affect the position numbers of both the camera and Player in the inspector menu when I would test this script out. Additionally, on the X axis, the rotation would be above 0 very slightly for some reason and I never managed to set it to 0 and I have no idea why but it is very unoticable so I left it in the end as everytime I tried to reset it, it would bounce back when I pressed enter to move on.

# 17/01/2025

Moving forward to making the Prototype, I know I wil be using the scripts I have been using up until now to make it which will save me a lot of time. However, I know some of them will need to be edited in order to work.

This turnt
