# iTunes-Playlist-Generator
SI 106 FINAL PROJECT README BY Dylan Rabin

This project is the “iTunes Playlist”. This project uses the iTunes Search API to allow users to create a playlist. My program allows users to search for an artist and to add songs from that artist into a playlist. It displays the album artwork for each song the user inputs, and then displays an audio preview for that song. 
The user is then asked whether he or she wants to add the song into the playlist; if the user says yes, the song will be stored in a text file called current_playlist. If the user decides to restart the kernel, the playlist will be restored the next time the code is run.

I am submitting 3 files: the Python Notebook called Final Project, the text file of playlist called current_playlist, and this README PDF file.

These are the modules needed to properly run my program:
from IPython.display import Image, from IPython.display import Audio, import requests, import json

HOW TO RUN THIS PROGRAM:
1. Open the Final Project.ipynb file in Jupiter Notebook
2. Run this code. The output will prompt you to either enter in an artist, look at your playlist, or exit.
3. It will then ask you whether you want to add the song to your playlist, not add and move to the next song for the artist, or go back to the main menu.
     a. If you enter ‘playlist’: It will give you your playlist from the ‘current_playlist.txt’ file, which already has songs in it.
4. If you exit the program, make sure to restart and clear output in Jupiter Notebook. When you re-run the code and type in ‘playlist’, It should give you the playlist from before.

HOW THE CODE WORKS (Final Project.ipynb):
Lines 1-4P Import Modules
Lines 7-12: defined Function makeItunesRequest(query) with one parameter, returns information about artist using iTunes API.
Lines 14-26: defined class Song() with __init__ method creating 5 variables, __str__ method returning “song by artist”, and method display_stuff() which displays artwork and audio for song.
Lines 28-35: try/except used to cache the playlist— reading current_playlist text file and loading string into python object, then trying to iterate through dictionaries to convert to Song objects if there are songs in the current_playlist. If there is nothing to append (no songs in playlist), then the code go directly to except to just create a new playlist list object.
Lines 40-72: The bulk of the program. While the program is running, the main menu is printed into the output, prompting the user to exit, see playlist, or enter artist name. It breaks out of the while loop if the user types in ‘exit’, reveals playlist if users types in ‘playlist’, and fetches song/artwork/audio from artist otherwise. 
Once the song/artwork/audio is revealed, the code asks the user for more input— whether the song should be added to playlist (‘yes’), not added (‘no’) or go back to main menu (‘back’). If the user says ‘yes’, the song is added to the playlist list and then is written into the cache file for current_playlist.txt. However, if the user says ‘no’, it continues with the for loop, and if the user says ‘back’, it breaks back with the main menu output.    


* Part of this code (makeItunesRequest() function) was taken directly from Problem Set 10, help was also received during Office Hours

