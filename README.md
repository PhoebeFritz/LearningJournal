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
