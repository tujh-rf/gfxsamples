# Greetings

Hello and warm welcome to the repository where is possible to find samples of using different APIs for the GFX development.

Most of samples will be the graphical development with Vulkan, OpenGL and Direct3D, however this is not the only way of developing applications with graphics. Sound, scripting and many other sides are also important and at the end here will be possible to find almost all of them.

Tutorials will use C++ as the main programming language but most of the time in the simple C-like way to make the code easier to understand for as many developers as possible.

To be able to build tutorials will be needed:

* git, to download the repo and some of dependencies from public repositories located on GitHub, GitLab or other platforms.
* CMake, no older than 3.25, to generate system specific build instructions, like Makefile for Linux or Microsoft Visual Studio solution for the Microsoft Windows.
* C and C++ compiler and linker, GCC as a default variant for the Linux or MSVC as a part of MS Visual Studio.
* System specific headers and libraries:
  * libX11, libXrand and etc for Linux
  * Windows SDK (including DirectX) for MS Windows.
