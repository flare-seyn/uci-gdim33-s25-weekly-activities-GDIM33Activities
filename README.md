


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
Answers:
1.Yes. Once the programmer finishes the dialogue system, a writer could add more dialogue without writing code by creating new DialogueNodeW4 ScriptableObjects, typing lines into them, and linking reply options to other dialogue nodes in the Inspector. The code and graphs already handle displaying the current node, generating buttons for reply options, and advancing to the next node when a button is clicked. Because the writer is mainly filling in data rather than changing system logic, they would not need to program new behavior for each extra conversation.
2.There is not really a hard limit in the system itself, because the writer can keep creating new DialogueNodeW4 assets and link them together into a larger conversation tree. The practical limit is mostly organization and UI space. Based on the activity instructions, the current UI can only show about 4 reply options at once before the screen runs out of room, so each individual node should stay within that visible choice limit. But the total number of nodes across the whole conversation can still grow very large.
3.The purpose of Regenerate Nodes is to rebuild Unity Visual Scripting’s node library so the graph editor knows what classes, methods, properties, and events are available as nodes. In this activity, it is especially important because PlayerReplyW4 is a custom class that does not inherit from Unity base classes like MonoBehaviour, so Unity does not automatically include it. Regenerating nodes updates the database used by Visual Scripting so that this type and its members can appear and be used inside the graphs.
