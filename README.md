# Project Lab Part 3: The final test

## Overview
In this part of the lab, you will be determining whether your auto-generated game from part 2 is actually solvable.


You will find the standard solutions to part 2 in the Project Lab 2 folder under Lab Assignments

## Part 1: Node class (~5 lines of code)
Create a Node class in Node.java that contains the following:
* Room value
* Node nextNode
## Part 2: Stack class (~25 lines of code)
Create a Stack class in Stack.java that implements a stack using a linked list. This will be used to hold Rooms you can explore.
1) Initialize the starting linked list node to be null
2) Implement boolean maybePushUnlockedRoom(Room room) which will create a Node and add it to the Stack only if that room is unlocked
3) Implement Room popUnlockedRoom() which will remove the Node from the Stack and return its room
4) Implement isEmpty() which will return if there are no more rooms to explore

## Part 3: In Main.java, Implement a method UnlockRoomsWithKeys(Node lockedRooms, Key newKey, Stack roomsToExplore) (~15 lines of code)
Upon finding new key, we want to use it and see if any of our previously locked rooms are now unlocked. Rather than traverse through the tree to find them, we can use our handy stack and queues
* For each room in lockedRoomKeys, check if newKey unlocks it
* If the room is unlocked by newKey, add it to the roomsToExplore Stack using maybePushUnlockedRoom and remove it from your linked list

## If you do not reach this point by the end of the first day, you are behind and not on track to finish on the second day of lab. Please come to office hours.

## Part 4: In Main.java Implement boolean IsGameWinnable(Room room)  (~20 lines of code)
To check if a game is winnable, we need to check all rooms we can reach.

### Part A: Rooms that are locked
Create an LinkedList to hold the Rooms that you've seen but are locked. 

### Part B: Rooms that are explorable
Create a Stack roomsToExplore and add room to it

### Part C: Put it all together
1) If we have no more rooms to explore and haven't found the treasure we cannot win
2) If there are rooms to explore
    1) Obtain a Room using popUnlockedRoom()
    2) Check if there is treasure. If there is, we can win!
    3) Otherwise, we must add the rooms we've discovered to our lockedRooms or roomsToExplore
    4) Lastly, let's check the keys we've found and see if they unlock any of our lockedRooms using the UnlockRoomsWithKeys method


## Part 4: In Main.java Implement Room generateWinnableRandomGame(int numKeys, int maxDepth) (~5 lines of code)
In this method, randomly generate TreeGames and test them with your isGameWinnable method until you find a game that can be won

## Part 5: Main.java main() (1 line of code)
Change Main.java main method to call generateWinnableRandomGame instead of generateTreeGame()

## Scheduling
Like for part 1 and 2, you must demo this project in person to get credit. Sign up here:
