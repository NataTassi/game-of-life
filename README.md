# Game of Life <img src="icon.png" width="25">

Python implementation of Conway's [Game of Life](https://en.wikipedia.org/wiki/Conway's_Game_of_Life).

<img src="https://i.imgur.com/0l7c18H.gif" title="Demo">

## Table of Contents
- [Intro](#intro)
- [Controls](#controls)
- [Patterns](#patterns)
- [Dependencies](#dependencies)
  - [Windows](#windows)
  - [Linux/Mac/others](#linuxmacothers)
- [Executable](#executable)
- [Notes](#notes)
- [License](#license)


## Intro
You can learn about the Game of Life rules on the first screen of the game along with some details about this implementation.

<img src="https://imgur.com/pIji02v.png" title="Intro">


## Controls
The game was provided with multiple features to give the user more control and provide a better experience. You can find the controls on the second screen of the game, and also you can access them at any time during the game.

<img src="https://imgur.com/yVMHvqb.png" title="Controls">


## Patterns

The initial pattern constitutes the seed of the system. The first generation is created by applying the game rules simultaneously to every cell in the seed. The image below is the initial seed of the game, so that you can start experimenting with a few patterns without the need of leaving the game. Then, you can create and save your own patterns. Note that, the initial seed was hardcoded into the game, that way you'll always have something to start with. You can find more patterns in the Wikipedia [entry](https://en.wikipedia.org/wiki/Conway's_Game_of_Life#Examples_of_patterns) or a vast collection of patterns [here](https://copy.sh/life/examples/).

<img src="https://imgur.com/dfPI9BL.png" title="Some patterns">


## Dependencies

The game was developed for [Python 3](https://www.python.org/downloads/) using Pygame, NumPy and Tkinter. For Windows, win32gui was used to solve a little issue. As the main GUI was built with Pygame but the dialog boxes were made with Tkinter, when a dialog box is closed on Windows the focus doesn't return automatically to the main window. So, it was necessary to take care of it manually, and this task was done with win32gui.  
Once the dependencies are satisfied, run the script as usual: ``` python GameOfLife.py ```

### Windows

```
pip install pygame numpy win32gui
```
You should have Tkinter already but if ```python -m tkinter``` command fails then your installation is broken. Reinstalling it should work, but more likely you forgot to check the tcl/tk and IDLE option when installing.

###  Linux/Mac/others
```
pip install pygame numpy 
```
Tkinter is not a pip package, so you have to get it with your package manager. For many of you, this should do the trick:
``` 
sudo apt-get install python3-tk 
```


## Executable
There's a [portable](/dist/GameOfLife.zip) program for Windows created with [Pyinstaller](https://www.pyinstaller.org/) in the dist folder of this project. Uncompress wherever you want to install the game and execute the exe file in there.


## Notes
* When you save a game the following values will be saved: current game state, states history, step-by-step flag, wraparound flag and speed.
* Once you load a saved game you can't go back to a previous game state because the states history is replaced by the one that is in the game you just loaded.
* If you delete the saves folder or the music folder, they will be automatically created the next time you open the game, but if you delete the saves folder during the game execution and then try to open a saved game, the game will crash because it's the first folder where it will look for your saves.
* If you change the amount of cells per axis manually (or other internal attributes for that matter), i.e., by changing the code, then your saved games won't be compatible with the current game internal settings and they will be recognized as corrupted.
* It's assumed that all the files in the music folder are audio files, if any. If you put other type of file in the folder, the player will try to read it and the game will crash. 
* You can use the uncopyrighted songs in the music folder to try the game music playback if you don't have any audio files to hand.


## License
[MIT](LICENSE)
