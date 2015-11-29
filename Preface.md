Welcome to this wiki/repository of Blender related python snippets. 

### First let's get the elephant out of the room

I might think of more things to say here at a later point but for now I want to stress that all this code is [licensed GPL3](). What does that mean? It means I would appreciate when you copy my code verbatim or (large sections) that you include the GPL3 license prominently in your add-on if you distribute it to others. I won't be bothered if you choose to ignore the licensing, but it's a politeness and people might call you out on it.

 and is intended to be only part of the learning process. I can show you endless examples of how to do things, but eventually you need to 'close the book' and get acquainted with the process of finding documentation and experimenting with Blender's python console to get better.

### Finding docs

In 2015 we got version independent docs:

    http://www.blender.org/api/blender_python_api_current/ 
    http://www.blender.org/api/blender_python_api_current/search.html?q=bmesh 
    http://www.blender.org/api/blender_python_api_current/mathutils.geometry.html 

I found the process of finding docs was a little slow so I coded an addon that uses Blender's Python console to execute non-python commands (Ctrl+Enter vs Enter). 