# DBW-Render

DBW-Render (or DBWRender) is an old ray tracing program, from the late 1980s. David Wecker wrote it on a DEC VAX minicomputer, and ported the result to the Amiga, which is the version I got to play with. Back then ray tracers were still a novelty on home computers, and many spent hours waiting for the image to draw (and further hours defining scenes by manually specifying the location of each geometric shape in a text file).

Given its age, the output from DBW-Render is pretty impressive: for its time, the shadowing algorithm produces very nice results:

![Glass Render](glass.png)

This is a Win32 console mode build of DBW-Render, based on John H. Lowery's MS-DOS port of David Wecker's Amiga original. The only changes I have made to the core ray tracer are to set the default image resolution to 800x600, increase the maximum resolution to 1600x1200, and set the colour depth to be 7 bits per colour component (from the original version's 4).

DBW_Render runs several orders of magnitude faster on a modern high-spec PC than it did on my Amiga A500 when I first encountered DBW_Render 15 years ago. For comparison, glass.dat would take over 12 hours to render on an Amiga with anti-aliasing on: now it takes a bit over two minutes, even though it is being rendered at a higher resolution. For a direct comparison, glassorig.dat renders the "glass" scene with exactly the same settings as used on the Amiga at 320x200: it takes 4 seconds on my PC!

In addition, I have written a completely new version of the Display program that shows the ray tracer's output. This version displays the image in a window and can optionally save the image out as a PNG file.

## Building

Download and install Visual Studio 2019 Community edition from https://visualstudio.microsoft.com/. In the installer, under "Workloads", make sure that "Desktop development with C++" is selected.

Install git. I use the version of git that is part of Cygwin, a Linux-like environment for Windows, but Git for Windows can be used from a Windows command prompt.

Open the environment that you are using git from (e.g. Cygwin), and switch to the root directory that the build environment will be created under. Clone this repository with git:
```
git clone https://github.com/DavidKinder/DBWRender.git
```
Start Visual Studio, open the solution "DBWRender/src/DBWRender.sln", then build the projects it contains.
