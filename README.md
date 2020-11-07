# IRI Legacy

# International Reference Ionosphere Software

The intention of this repository is:

- Create a copy of the legacy software

- Keep the software as written in Fortran 77, making as few changes as possible.

- Use CMake to generate projects for compiling the software

- Compile the software using the Mingw version of gfortran in Windows 10

# Looking for IRI-2016?

This repository does not contain IRI-2016.  If you are looking for IRI-2016, go to either

http://irimodel.org/

or

https://github.com/space-physics/iri2016

The space-physics repository has the IRI-2016 Fortran software and includes support for Python and Matlab.  Sample runs are included and the issues section is active, so if you need support, go to the space-physics repository.

# Looking for IRI-2012, IRI-2007, IRI-2001, IRI-95, or IRI-90?

This is one source for the legacy versions of IRI Fortran software.

# IRI-Model

A copy of the legacy Fortran source code was downloaded from:

http://irimodel.org/

# UMASS Lowell

UMass Lowell made a Windows version of IRI-2001, which can be downloaded from:

https://ulcar.uml.edu/digisonde.html

Look for the heading of 'Other Software', and click on 'IRI-2001 WINDOWS' to download a zip file with the program and data files.  A copy of the zip file is included in this repository.

# CCMC Community Coordinated Modeling Center

https://ccmc.gsfc.nasa.gov/modelweb/

CCMC has an archive of IRI software at:

https://ccmc.gsfc.nasa.gov/pub/modelweb/ionospheric/iri/

Including iri90, iri95, iri2001, iri2007, and iri2016.  A copy of these archives are included in this repository.

## Compiling of legacy Fortran software

Use CMake to generate project files.  Be sure to add a 'build' folder before configuring with cmake.

For Windows users, in order to get a working installation of gfortran along with a fairly easy to learn IDE, it is recommended to download Code::Blocks 20.03 from:

http://www.codeblocks.org/

In particular, select the installer that includes Mingw.  This mingw-setup installer will install CodeBlocks and GCC, which includes gfortran version 8.1.0:

`codeblocks-20.03mingw-setup.exe`

When generating project files with CMake, select 'CodeBlocks - MinGW Makefiles', and 'use default native compilers'.

Then the CodeBlocks project should be in the 'build' folder, open the project and rebuild.

The iri test executable file will be placed in the 'build/bin' subfolder.

One will need to copy data files needed by iri test into the 'build/bin' subfolder.


