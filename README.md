# Tic Tac Toe!

## Implementation
My design process was essentially just following the comments that were laid out to me in the `TicTacToe.cpp` file. They were pretty clearly laid out, so props to whoever wrote those comments! If something was not clear, I asked about it on Discord or just stared at it until the solution came to me.

## Platform used
I used Windows 10 (x64) for this project.

## Issues
There was a slight hangup for me for getting the resources to load, so I had to make a small change to `Sprite.cpp`. Specifically, I had to change the file path from `resources` to `..\resources`. This resulted in `square.png` and the other assets to load properly. Without the file path change, the assets failed to load. Professor Devine mentioned that this is likely due to a bug between the CMakeLists.txt file and my build not being compatible, as it should have copied the `resources` directory next to where my build was. Unfortunately, that didn't happen :(

## Extra Credit
I put two buttons in the settings menu that let you play against the AI or play against another person. The AI itself is a simple random AI -- it searches for empty spots and randomly picks one. I also was not familiar with how random numbers and choices were generated in C++ and I gotta say, it's not something I am used to quite yet. Maybe I'm spoiled by C#, JavaScript, and other languages that just have a built-in `Random()` function!