This is a Win32 console mode build of DBW_Render, based on John H. Lowery's
MS-DOS port of David B. Wecker's Amiga original. The only changes I have
made to the core ray tracer are to set the default image resolution to
800x600, increase the maximum resolution to 1600x1200, and set the colour
depth to be 7 bits per colour component (from the original version's 4).

This version has been built with GCC with settings turned on to optimize
for speed. The result is that DBW_Render runs several orders of magnitude
faster on a modern high-spec PC than it did on my Amiga A500 when I first
encountered DBW_Render 15 years ago. For comparison, glass.dat would take
over 12 hours to render on an Amiga with anti-aliasing on: now it takes
a bit over two minutes, even though it is being rendered at a higher
resolution. For a direct comparison, glassorig.dat renders the "glass"
scene with exactly the same settings as used on the Amiga at 320x200:
it takes 4 seconds on my PC!

In addition, I have written a completely new version of the Display
program that shows the ray tracer's output. This version displays the
image in a window and can optionally save the image out as a PNG file.
