# 6502 assembly language Mandelbrot Set plotter

Inspired by Gordon Henderson's BASIC Mandlebrot benchmark: 
[https://projects.drogon.net/retro-basic-benchmarking-with-mandelbrot/]

I wanted to make one in pure 6502 assembly language to see how fast it would run
on my computer.  I used a different fixed-point format, with 24-bit multiplication
to handle overflow.

I used roughly the same characters as Gordon, but added some extras and repetitions 
to allow for more iterations.  I'm also rendering a different region, tailored to
suit my PC's console window font.

If you want to try it, it requires the "xa" assembler to built it.  Additionally, 
it requires that you provide routines to print characters to the output stream:

* printchar  - output the character whose ASCII code is in A
* printimm   - output the null-terminated string following the JSR instruction

For my system these are provided by the OS and boot64.inc defines their addresses
within the OS ROM - you need to provide your own definitions somehow.

