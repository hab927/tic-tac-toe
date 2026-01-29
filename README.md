# Tic Tac Toe!

## Implementation
My design process was essentially just following the comments that were laid out to me in the `TicTacToe.cpp` file. They were pretty clearly laid out, so props to whoever wrote those comments! If something was not clear, I asked about it on Discord or just stared at it until the solution came to me.

## Platform used
I used Windows 10 (x64) for this project.

## Issues
There was a slight hangup for me for getting the resources to load, so I had to make a small change to `Sprite.cpp`. Specifically, I had to change the file path from `resources` to `..\resources`. This resulted in `square.png` and the other assets to load properly. Without the file path change, the assets failed to load. Professor Devine mentioned that this is likely due to a bug between the CMakeLists.txt file and my build not being compatible, as it should have copied the `resources` directory next to where my build was. Unfortunately, that didn't happen :(

## Extra Credit
I put two buttons in the settings menu that let you play against the AI or play against another person. The AI itself is a simple random AI -- it searches for empty spots and randomly picks one. I also was not familiar with how random numbers and choices were generated in C++ and I gotta say, it's not something I am used to quite yet. Maybe I'm spoiled by C#, JavaScript, and other languages that just have a built-in `Random()` function!

# Negamax AI

## Implementation
The implementation is largely based on Tuesday (1/26/26)'s live coding session that Prof. Devine did. It did help deepen my understanding, and by the end of the class, we had a mostly-working negamax function. The only parameter I had to change was the `playerColor` evaluation in recursing `negamax()` calls.

As for how the AI works:
1. Each time it's the AI's turn, it goes through every empty space on the board. For each empty space, it places its piece on it and evaluates the next step of the game. This happens for all possible states of the game (unless you have Alpha-Beta pruning).
2. Every time the AI sees a terminal state, one of two things will happen. Either the Human wins or the AI wins. If the AI wins, Negamax will return -10 and this will be received as -(-10) by the function, resulting in a "good" value of +10. On the contrary, a Human victory means a "bad" value of -10, following similar logic.
3. This happens recursively and Negamax eliminates all suboptimal paths and chooses the best move every time. Therefore, it is nigh-unbeatable.
4. **(EC)** I added alpha-beta pruning, which essentially sigificantly cuts down on the amount of nodes used to search for the best possible move. This is done by introducing a lower and upper bound for the nodes (thank you Wikipedia for the explanation!)