# CanvasWM

$${\color{red}Development \space Just \space Begun \space - \space Not \space Usable \space Yet}$$

CanvasWM is an experimental hybrid Wayland compositor built on wlroots and tinywm. CanvasWM has three different modes of operation:
1. Floating - Acts as a normal floating window manager (e.g. Plasma, Cinnamon)
2. Tiled - Acts as a normal tiling window manager (e.g. Hyprland, i3)
3. Canvas - Emulates a nearly infinitely large canvas to move windows aswell as the camera around on (just out of curiosity, also not a thing yet if I am not mistaken)

Behind the scenes the canvas mode is always in use, but for floating mode and tiled mode the camera is restricted to screen-sized portions. The camera is allowed to move up and down, left and right, but in it snaps to a grid, where every cell is the size of your screen.

Thanks a lot for checking out CanvasWM! If you are interested by the concept please check back later, when the project is in an unsable state!
