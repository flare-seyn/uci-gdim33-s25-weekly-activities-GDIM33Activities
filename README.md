


# Week1 in class


## Actitivy 1 Brainstorming

1. pattern: inspirtation from slay the spire maybe
maybe kind of dungeon adventuring, player collecting objects and clues to advance to the next area and snowballing to defeat a final boss

2
Chat with at least one of your table mates about what they’re interested in building. How are your personal styles and interests similar?
they seem to already have a big picture in mind while im still exploring

3
Chat with your table's LA about their taste in games. How are their tastes similar to yours?
 LA initially said the second line was too specific and then i mentioned slay the spire like everyone i know is playing it and he agreed on that kind of "peer pressure"


## Actitivy 2 Break down
<img width="800" height="800" alt="image" src="https://github.com/user-attachments/assets/da406662-4c49-4103-b8d8-46672c2d8a6e" />

genre seems to be 2D platformer.

# Week 3 In class

## Activity 1 
<img width="400" height="600" alt="image" src="https://github.com/user-attachments/assets/5c640c18-10c9-4ba3-8429-f8d483b1caa2" />   <img width="400" height="500" alt="image" src="https://github.com/user-attachments/assets/bcaa1d26-9fab-49a4-a5d3-ae217379d922" />

## Activity 2

Saving the event name for the explore-to-dialogue transition as a Scene variable like clickNpcEventName is advantageous because it lets me keep that event name in one place instead of typing the same string in multiple parts of the graph. That makes it easier for me to stay consistent and reduces the chance of spelling mistakes breaking the transition. If I ever need to rename the event later, I only need to update the variable instead of searching through every graph that uses it.

Using a Debug.Log() node helped me test my graphs at an intermediate step because it let me check whether a certain event or transition was actually being reached before the full system was working. For example, I could use it to confirm that an interaction, collision, or state change was happening when I expected it to. That was helpful because it let me narrow down whether the problem was with the trigger itself or with a later part of the graph.

The Set Cursor Lock State is not very relevant to my Vertical Slice because my project is a 2D platformer, not a 3D game that depends on mouse-look camera control. My player mainly uses keyboard movement and simple interaction, so locking the cursor would not really affect the main gameplay experience. Because of that, it is not something I would prioritize in my slice.

The concept of a game state is relevant to my Vertical Slice because my game still has different overall phases, even though it is a small project. For example, there is a gameplay state where the player can move, jump, fight, and interact, and there could also be a lose state or level-complete state where normal controls stop and the game responds differently. Thinking about game states helps me organize the experience more clearly and makes the game feel more complete


# Week 4 In Class


## Activity 1: playtesting
My main goal is to test the game playability and the basic instructions are directly inserted in the itch.io gamepage.
hidden mechanics expected; normal jumping will be extreme dangerous, a speciial strategy is designed and during the test i will monitor if other guys can figure it out.
playable: basic 1 level challenge: dodge a patrolling mob and spike trap( most visbible and permanent one.
playtest group members:
beiduo jin, OKADA Naoma , Nansong Sun
playtesting notes:
playetesters spent a few attempts to figure out the hidden direction that direct crossing is not feasible, but jumping at the edge of the platform and straightly move over the mob and jump to the final platform before it figures out the case and turn back to chase)

## Activity 2 
1. Assuming this activity is completed by a programmer, could a writer add more dialogue to this setup without writing any code? Why or why not?

Yes, a writer could add more dialogue to this setup without writing any code, as long as the programmer has already completed the dialogue system itself. In this activity, the actual conversation content is stored in DialogueNodeW4 ScriptableObjects and in their reply options, not hard-coded directly into the graph each time. That means a writer can create new dialogue node assets, type new lines into the Line field, and connect reply options to other dialogue nodes in the Inspector. The graph and scripts already handle showing the current line, creating buttons for each reply option, and moving to the next dialogue node when a button is clicked. Because of this, the writer is mainly editing content data rather than changing the system’s logic.

2. What limit is there to the number of dialogue nodes that the writer could create without writing any code?

There is not really a strict limit to the total number of dialogue nodes the writer could create without writing code. The writer can keep making more DialogueNodeW4 ScriptableObjects and link them together into a larger branching dialogue tree. The real limitation is more about usability and organization than programming. For example, the activity notes that the current UI can only comfortably fit about four reply options on the screen at one time before it runs out of space. So while one dialogue node should not have too many reply options at once, the overall conversation can still contain many different nodes. In other words, the number of nodes is flexible, but the number of visible choices at one moment is limited by the interface.

3. In your own words, describe the purpose of the "Regenerate Nodes" button.

The purpose of the Regenerate Nodes button is to rebuild the Visual Scripting node library so Unity knows what classes, variables, methods, and properties should be available as nodes in graphs. In this activity, that matters because PlayerReplyW4 is a custom class and Unity does not automatically expose every custom type to Visual Scripting. By adding the type in the Visual Scripting settings and pressing Regenerate Nodes, Unity updates the database that the graph system uses, which makes those custom types and their members available as nodes. Without doing this, the graph may not recognize the class correctly or give access to the data needed for the dialogue system.


# Week 5 In class

## Activity 1: Task Break-down

Feature: Build the first playable dungeon level using Unity Tilemaps

Big Step 1: Create the simplest playable Tilemap level
This step focuses on building the minimum version of the level so the player can move through it.

Create a Grid object and a Tilemap in the scene for the ground and platforms.
Test: Run the game and confirm the Tilemap is visible in the scene.
Paint a small stretch of ground and at least one raised platform.
Test: Run the game and confirm the player can stand on the tiles visually.
Add a Tilemap Collider 2D so the player does not fall through the tiles.
Test: Run the game and confirm the player collides correctly with the floor and platform.
Add a gap or simple jump section in the Tilemap.
Test: Run the game and confirm the player must jump to cross it.

Big Step 2: Add hazard and level progression using the Tilemap layout
This step makes the level feel more like an actual game area instead of only a movement test.

Paint a hazard area, such as spikes or a dangerous pit, into the level layout.
Test: Run the game and confirm the hazard is visible and placed where the player can encounter it.
Add collision or trigger logic so the hazard damages or resets the player.
Test: Use a Debug.Log() or run the game and confirm the message/action happens when the player touches the hazard.
Add a simple end area, such as a door, flag, or goal platform.
Test: Run the game and confirm the player can reach the end area.
Add a trigger at the end area to detect level completion.
Test: Use a Debug.Log("Level Complete") and confirm it prints when the player reaches the goal.

Big Step 3: Expand the Tilemap level into a more recognizable dungeon slice
This step adds a little more structure and visual clarity to match the planned game.

Add wall tiles and shape the level so it looks more like a dungeon space instead of floating blocks.
Test: Run the game and confirm the level looks more intentional and readable.
Separate the layout into a start area, challenge area, and exit area.
Test: Run the game and confirm the player can clearly move through the level in sequence.
Add one enemy or obstacle into the Tilemap-based level.
Test: Run the game and confirm the player can encounter it in the intended section.
Adjust tile placement to make jumps, hazards, and progression feel fair.
Test: Play through the level from start to finish and confirm it is possible to complete.

## Activity 2: What I accomplished in class today

Today, I worked on integrating my Unity system, Tilemaps, into my game by building the first version of my dungeon level. I created a Grid and Tilemap, painted ground and platform tiles, and added collision so the player could walk and jump on the level correctly. After that, I added a simple jump gap to make the level function more like an actual platformer instead of just a flat test scene.

After getting the basic layout working, I added a hazard section and started building a clearer level flow with a start area and an end area. I used testing in Play mode and debug messages to check whether the player could move through the level, collide with the tiles correctly, and trigger hazards or the goal as expected. By the end of class, I had a more playable level structure that used Tilemaps as an actual gameplay system rather than only as background decoration.
I also received ideas and suggestions about scriptable objects description and the roadmap to work on it.



# Week 6 IN Class

## Activity 1: playtesting
link: https://11122233444444.itch.io/gdim33-vertical-slice-2
goals: testing bugs and adjusting difficulty level.
new features since last playtest:Expanded the game from two levels to four levels, adding Level 3: Split Route Atrium and Level 4: Exit Gauntlet with new platform layouts, hazards, moving platforms, bounce pads, dash-refresh orbs, crumble platforms, relics, enemies, and final gauntlet progression. 
Added more variable completion methods through unlockMode: Level 3 can unlock through relic collection or enemy defeat, while Level 4 requires relic collection and enemy defeat. 

playtesting notes: the pickup was easily figured out but the tester wasnt aware of the existance of the lift before i directly told them(
testers figured out the mechanic of killing mobs after several attempts;
suggestion from the tester is mainly on making a transitioning betweeen each stages\

## Actitivy 2 
1.The Multiply setting makes the resulting color darker and less saturated because RGB values are stored between 0 and 1. When two color channels are multiplied together, the result usually becomes smaller. For example, 0.8 × 0.5 = 0.4, so the final color loses brightness. Since each red, green, and blue channel is reduced this way, the blended color looks darker and less intense.
2.If we use Multiply to combine Alpha values, the result will usually be more translucent than either original value. This is because alpha values are also between 0 and 1, so multiplying them makes the final alpha smaller. For example, 0.5 × 0.5 = 0.25, which means the object becomes more transparent.
3.The shader gets the UV values from the mesh itself. The Sphere or Shiba model has UV coordinates saved as part of its mesh data. Unity’s UV0 node reads those coordinates and uses them to tell the shader which part of the texture should appear on each part of the object.
4.Yes, manipulating colors with math sounds interesting because it shows that shaders are not just about picking colors manually. By using math nodes like Blend, Multiply, Split, and Sample Texture 2D, I can create effects such as tinting, transparency, darker color mixing, or ghost-like materials. It makes shaders feel more flexible because one graph can create many different visual results depending on the material settings


# Week 7 In class


1.The data for the Vertex Color node came from the Shiba mesh itself. Each vertex in the mesh stores different kinds of data, including position, normal, tangent, UV, and color. The Vertex Color node reads that stored color data from each vertex and sends it into the shader.


2.The colors are blended at the edges because vertex color exists only on the vertices, not every pixel. When the fragment shader draws the polygons, Unity interpolates the vertex colors across the surface between nearby vertices, which creates smooth blending instead of sharp color borders.


3.The vertex-colored Shiba is less detailed because the color information depends on how many vertices the mesh has. A texture can store many more color details using pixels, so it can show sharper patterns and smaller features. Vertex color is useful for simple color variation, stylized low-poly art, masks, gradients, quick debugging, or adding lightweight color information without using a full texture.


4.Yes, something looks wrong with the mesh’s vertex normals. The activity notes that the Shiba’s vertex colors show an issue on the back-left leg, which suggests some normal data may be incorrect or inconsistent there.


5.Another piece of data I could test with a debug shader is UV coordinates. For example, I could output the UV values as colors to see whether the texture coordinates are stretched, flipped, or mapped incorrectly. This would be useful when a texture looks distorted on a model.


6.The lighting error happens because the Main Light Direction vector is pointing toward the Shiba, while the Shiba’s surface normals point outward from the mesh. When the dot product compares two vectors facing opposite directions, the result becomes negative, making the surfaces facing the light appear dark and the back-facing surfaces appear bright. Multiplying the light direction by -1 fixes the comparison.

# Week 8 In class

link:https://11122233444444.itch.io/gdim33-vertical-sliece-3
new: added a loop system added new trap type and improved player model and several effect
goal: test overall loop, digging potential bugs

notes: the playtester payed some effort to understanad core mechanics through gameplay and several bugs were detected., it was not needed for external help when player was exploring options and mechanics

Activity 2C Devlog Questions
 
1. Open the Frame Debugger window. What's the name of the pass associated with the post-processing effect we created? Other than the name being kinda obvious, how can you tell?

The pass associated with the post-processing effect is FullScreenPassRendererFeature. I can tell because this renderer feature uses the PostEffect material as its Pass Material, and the effect changes the entire screen instead of only changing one object. The shader samples the BlitSource, which represents the game’s color buffer, so it is using the image already drawn to the screen and applying a full-screen effect on top of it. In the Frame Debugger, this shows up as an extra full-screen rendering pass after the main scene has already been rendered.

2. What does the screen look like if the Lerp value is set to 0.5? What about 0? What about 1?

If the Lerp value is 0, the screen looks normal because it only shows the original game screen from BlitSource. If the Lerp value is 1, the screen shows the full post-processing effect, so the red cobblestone texture overlay is strongly applied across the whole screen. If the Lerp value is 0.5, the screen is halfway between the original game screen and the red overlay effect, so the red texture is visible but only partially blended in.

3. WHY does the screen look like that based on those different Lerp values?

The screen changes because the Lerp node blends between two inputs. The first input is the original game screen from BlitSource, and the second input is the modified version where the original screen is multiplied by the red effect texture. A Lerp value of 0 means it uses only the first input, so the screen stays normal. A value of 1 means it uses only the second input, so the red effect is fully visible. A value of 0.5 means it blends equally between the two, making the effect appear at half strength.

4. Why does our algorithm for the Lerp amount use (sin(time)+1)/2 instead of just sin(time)?

The Lerp value is supposed to stay between 0 and 1, but sin(time) gives values from -1 to 1. When the value goes below 0, the Lerp can behave in an unintended way, which is why the screen can get weirdly bright during the animation. Using (sin(time)+1)/2 fixes the range. Adding 1 changes the range from -1 to 1 into 0 to 2, and dividing by 2 changes it into 0 to 1. This makes the red post-processing effect smoothly pulse between no effect and full effect without going outside the valid Lerp range.
