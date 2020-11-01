# IRI

# International Reference Ionosphere Software

This is a copy of the Fortran source code from:

http://irimodel.org/

The intention of this repository is:

- Create a copy of the software

- Keep the software as written in Fortran 77, making as few changes as possible.

- Use CMake to generate projects for compiling the software

- Compile the software using the Mingw version of gfortran in Windows 10

- Include all four versions of the software

## Compiling

Use CMake to generate project files.

For Windows users, it is recommended to download Code::Blocks 20.03 from:

http://www.codeblocks.org/

In particular, select the installer that includes Mingw:

`codeblocks-20.03mingw-setup.exe`

When generating project files with CMake, select 'CodeBlocks - MinGW Makefiles', and 'use default native compilers'.

Then the CodeBlocks project should be in the 'build' folder, open the project and rebuild.

The iri test executable file will be placed in the 'build/bin' subfolder.

One will need to copy data files needed by iri test into the 'build/bin' subfolder.


