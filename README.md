# IRI

# International Reference Ionosphere Software

The intention of this repository is:

- Create a copy of the software

- Keep the software as written in Fortran 77, making as few changes as possible.

- Use CMake to generate projects for compiling the software

- Compile the software using the Mingw version of gfortran in Windows 10

- Include all versions of the software

This contains a copy of the Fortran source code from:

http://irimodel.org/

# UMASS Lowell

UMass Lowell made a Windows version of IRI-2001, which can be downloaded from:

https://ulcar.uml.edu/digisonde.html

Look for the heading of 'Other Software', and click on 'IRI-2001 WINDOWS' to download a zip file with the program and data files.

# CCMC Community Coordinated Modeling Center

https://ccmc.gsfc.nasa.gov/modelweb/

CCMC has an archive of IRI software at:

https://ccmc.gsfc.nasa.gov/pub/modelweb/ionospheric/iri/

Including iri90, iri95, iri2001, iri2007, and iri2016.

## Compiling of software from IRIModel.org

Use CMake to generate project files.

For Windows users, it is recommended to download Code::Blocks 20.03 from:

http://www.codeblocks.org/

In particular, select the installer that includes Mingw.  This mingw-setup installer will install CodeBlocks and GCC, which includes gfortran version 8.1.0:

`codeblocks-20.03mingw-setup.exe`

When generating project files with CMake, select 'CodeBlocks - MinGW Makefiles', and 'use default native compilers'.

Then the CodeBlocks project should be in the 'build' folder, open the project and rebuild.

The iri test executable file will be placed in the 'build/bin' subfolder.

One will need to copy data files needed by iri test into the 'build/bin' subfolder.


