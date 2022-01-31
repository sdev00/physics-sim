# Physics Simulator
Experimental Project by Sahil Dev

### Motivation
I saw an interesting post, where someone set up initial conditions in a physics environment (e.g. circles making a smiley face) then reversed time (for ~3 seconds) to get a random-looking starting position. Then when time was set to move forward again, it looked like out of the randomness, the starting pattern emerged miraculously in the middle of the simulation, before chaos took over again.

I found that idea fascinating and decided to try implementing my own version.

### How to Run
You should just be able to open the .ipynb file in Jupyter notebook. You will need to install the pygame, pygame-menu, and numpy packages if you have not already.

### Controls
#### Play
* `L` = forward
* `K/Space` = pause/play
* `J` = backward
* `F` = fast-forward*
* `S` = slow-motion*
* `.` = step one frame forward**
* `,` = step one frame backward**
* `D` = toggle shadows***

\* works for forward or backward \
\** only works when paused \
\*** causes huge issues with framerate

#### Create
* Left click: place a normal-gravity ball
* Right click: place a reverse-gravity ball
* Middle click: place a no-gravity ball
* Spacebar: place a light-source ball
* Click an existing ball to delete it
* `C` = clear board

### Notes
* This only works because I've built a deterministic simulation
    * If any randomness was involved, it would make going backwards impossible
* It's not a perfect simulation
    * Collisions still are a bit off (treats circles as point masses), maybe I'll fix that eventually
* Limited precision (80 bits with numpy.longdouble) make it impossible to always get the same starting position again in such a chaotic system
    * For example, going back to time t = -10 and then going forward to time t = 0 again will probably yield something that looks similar, but noticeably different from what position you actually had set up
* There are lots of bugs and TODO's. I know.

### Resources and Libraries
* [Jupyter Notebook](https://jupyter.org/)
* [Pygame](https://www.pygame.org/)
* [numpy](https://numpy.org/)
* Khan Academy - [elastic collisions video](https://www.khanacademy.org/science/physics/linear-momentum/elastic-and-inelastic-collisions/v/how-to-use-the-shortcut-for-solving-elastic-collisions)
* [Shadow calculations](http://www.ambrsoft.com/TrigoCalc/Circles2/Circles2Tangent_.htm)