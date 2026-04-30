


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
