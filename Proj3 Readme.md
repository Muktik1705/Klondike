🌀Solitaire

Solitaire (Klondike) is a classic single-player card game where the goal is to move all cards to four suit-based foundations in ascending order.
This is a Solitaire card game built in C++ using SFML. 

It applies object-oriented design principles and leverages graphical components from SFML (e.g., sf::RenderWindow, sf::Sprite, sf::Texture, sf::Event) to provide an interactive Solitaire gameplay experience with smooth animations and user interaction.

✨ Why Is It Special?

Solitaire is timeless—easy to learn, endlessly engaging, and the perfect blend of strategy, planning, and luck, all in a single-player experience.

🕹️ How to Play:

Flip cards from the stock to uncover new moves.

Build sequences in the tableau by stacking cards in descending order and alternating colors.

Reveal hidden cards by clearing columns.

Move Aces to the foundations, then build each suit from Ace to King.

Win by moving all cards to the foundations!



🗃️ Project Structure & File Roles

src/	                          Contains the source code files implementing the game's logic and functionality.
resource/	          Holds graphical assets and other resources used in the game.
CMakeLists.txt	  Configuration file for building the project using CMake.
README.md	          Provides an overview and instructions for the project.
.gitignore	          Specifies files and directories to be ignored by Git.

📊 src/ Directory Breakdown

File | Description
Card.cpp / Card.h | Defines the Card class — manages card properties (rank, suit, face-up state) and rendering via SFML.

Deck.cpp / Deck.h | Implements the card deck — handles creation, shuffling, and card distribution logic.

Game.cpp / Game.h | Core game controller — manages the logic, user input, event handling, and rendering loop.

Pile.cpp / Pile.h | Implements a generic pile of cards — base for tableau, foundation, and stock piles.

Stock.cpp / Stock.h | Specialized pile for the stock (draw pile) behavior — includes drawing and flipping mechanics.

Tableau.cpp / Tableau.h | Manages the tableau (main play area) — handles rules for moving and revealing cards.

main.cpp | Entry point of the program — initializes the game window and starts the game loop.

main.cpp	Entry point of the program — initializes the game window and starts the game loop.


🧬 Data Structures Used
Data Structure | Description / Usage

std::vector | Used extensively for dynamic arrays of Card* objects in piles like tableau, foundation, and stock.  |  
   
   this was very improtant as this is what enebles for it to move multiple cards at once. We first transphur each card that needs to be transphured to a stack, and the temporary empty the stack in the target location. 
the main reason for using this is to coordinate the start and end point, which requres a vector(or an array).

std::stack | Employed to manage temporary card movements (where LIFO behavior is needed). this code doesn't have undo options, otherwise it would have beed used therre as well.  |  mentioned in vector.

std::deque | Used in some piles for flexible push/pop from both ends, especially for card recycling.  |  the input dech that is on the top right of the game. 

std::array | Used when a fixed number of piles (e.g., 7 tableau piles, 4 foundations) is required.  |  

std::string | For storing card names, file paths, or user messages.

enum | Enumerations used to define Suit, Rank, PileType, or game states.

struct / class | Custom data structures like Card, Pile, Deck, Game, and Tableau encapsulate game logic and state.

std::map or std::unordered_map | (Optional/inferred) — may be used for texture or resource management, though not prominent in core gameplay.





🌐 Download the Project

To build the game, you will need to install the SFML library:

https://www.sfml-dev.org/download/sfml/2.5.1/

You will also need cmake with a version upper or equal to 3.17

for windows
```
pip install cmake
```
OR

for Ubuntu
```
sudo apt  install cmake  # version 3.27.8-1build1
```
Next clone the source files by
```
git clone https://github.com/Muktik1705/Klondike.git
```
Build:
After cloning the repository enter the following commands to build the game:
```
cmake . -B build

cmake --build build
```
To Run
```
./Klondike
```
