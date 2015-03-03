## MECAGEN - A Simulation Platform of Animal Embryogenesis

[MECAGEN](http://www.mecagen.org) is a C++ simulation platform for animal morphogenesis relying on a realistic agent-based model. It is centered on the physico-chemical coupling of cell mechanics with gene expression and molecular signaling.

This project aims to investigate the multiscale dynamics of the early stages of biological morphogenesis. Embryonic development is viewed as an emergent, self-organized phenomenon based on a myriad of cells and their genetically regulated, and regulating, biomechanical behavior.

### Getting Started

#### Install on Linux

##### Dependencies

Installing MECAGEN requires a few libraries to be installed first. All of these libraries can be installed manually via the hyperlinks. Yet, using a package manager simplifies this prerequisite step. We provide APT command lines operative on Ubuntu/Debian, alternative package manager have also been tested (e.g. pacman on Archlinux).

* SDL2.0 ([Simple DirectMedia Layer](https://www.libsdl.org/download-2.0.php), not to be mistaken with the previous version SDL1.2)
```shell
sudo apt-get install libsdl2-dev
```
 
* GLEW ([The OpenGL Extension Wrangler Library](http://glew.sourceforge.net/))
```shell
sudo apt-get install libglew-dev
```

* GLUT ([The OpenGL Utility Toolkit](https://www.opengl.org/resources/libraries/glut/))
```shell
sudo apt-get install freeglut3-dev
```

* [Boost Serialization](http://www.boost.org/doc/libs/1_57_0/libs/serialization/doc/index.html) 
```shell
sudo apt-get install libboost-serialization-dev
```

* [Boost Random Number Library](http://www.boost.org/doc/libs/1_57_0/doc/html/boost_random.html)
```shell
sudo apt-get install libboost-random-dev
```

* [QT5.x](http://qt-project.org/downloads)
```shell
sudo apt-get install qt5-default
```

The QT library folder must be in the LIBRARY_PATH environment variable and the folder containing the Meta-Object Compiler (moc) program in the PATH environment variable.

* (Optional but recommended) [CUDA 5.5](https://developer.nvidia.com/cuda-toolkit-55-archive) or newer

Cuda is required to enable an enhanced rendering of the simulations. It uses Vertex Buffer Object to interoperate with OpenGL. 
```shell
sudo apt-get install nvidia-cuda-toolkit
```

* (Required only if no Cuda is installed) [Thrust](http://thrust.github.io/)

Thrust is included with Cuda. Yet if you install MECAGEN without Cuda, the Thrust header library must be installed manually. Thrust is a C++ template library so the files just need to be copied on your system.

##### Compilation


First, edit the [mecagen makefile](mecagen/Makefile) by adding your installation paths for QT and (Cuda or Thrust).

Then, decide whether which custom version of MECAGEN you want to use. Indeed, one of the specificities of the MECAGEN platform is the possibility to integrate external customization code to simulate specific structures and behaviors such as for example extra-embryonic tissue. Currently, two custom version are available: the "default" custom version performs regular MECAGEN simulation without specific structures or behaviors, and the "zebrafish" custom version adds rules for the yolk cell and the enveloping layer. 

It is not currently possible to compile both custom version at the same time so you have to choose whether you want to compile the default version

```shell
make CUSTOM=default
```

or the zebrafish version

```shell
make CUSTOM=zebrafish
```

Moreover, if Cuda is installed on your system, we recommend that you compile MECAGEN with the VBO/Cuda version of the cells rendering by invoking "USE_VBO=1" with the make command line.

```shell
make CUSTOM=default USE_VBO=1
```

or 

```shell
make CUSTOM=zebrafish USE_VBO=1
```

#### Generate and run examples

Intro explain xml small cpp file to specify initial state and parameters
All examples are compiled by:

##### Generate input files

écrire make example script -> done


##### Run examples

Verify that the examples' input file have been generated

écrire run script -> ...


### License

MECAGEN is released under the GNU General Public License v3.0; see LICENSE for more details.

