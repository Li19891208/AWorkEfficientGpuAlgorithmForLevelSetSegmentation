<p align="center">
  <strong><a href='http://graphics.stanford.edu/papers/gpu_level_set/'>A Work-Efficient GPU Algorithm for Level Set Segmentation</a></strong><br>
  Mike Roberts, Jeff Packer, Mario Costa Sousa, Joseph Ross Mitchell<br>
  <em>High Performance Graphics 2010</em>
</p>

<a href='http://graphics.stanford.edu/papers/gpu_level_set/'>![Alt text](/documentation/results/Brainweb-3D-Composite-1-6.png)</a>

This repository contains a C++/CUDA implementation of our paper <a href='http://graphics.stanford.edu/papers/gpu_level_set/'>A Work-Efficient GPU Algorithm for Level Set Segmentation</a>. The source code and precompiled binaries available here are provided for non-commercial research purposes only.

### Requirements

* Windows XP/Vista/7/8
* Visual Studio 2008
* <a href='https://developer.nvidia.com/cuda-gpus'>CUDA-Enabled GPU</a>
* <a href='https://developer.nvidia.com/cuda-downloads'>CUDA drivers</a>
* <a href='http://graphics.stanford.edu/papers/gpu_level_set/github/AWorkEfficientGpuAlgorithmForLevelSetSegmentation/sdk.zip'>SDK zip file</a>

### Precompiled Binaries

Precompiled binaries are available <a href='http://graphics.stanford.edu/papers/gpu_level_set/github/AWorkEfficientGpuAlgorithmForLevelSetSegmentation/bin.zip'>here</a>. If you intend to run the precompiled binaries and you don't have Visual Studio 2008 installed, you'll need the <a href='http://www.microsoft.com/en-us/download/details.aspx?id=29'>Visual Studio 2008 Visual C++ Redistributable Package (x86)</a>.

### Build Instructions

* Unzip the SDK zip file into the code folder such that the sdk folder is parallel to the gpuseg folder.
* Open code\gpuseg\build\gpuseg.sln in Visual Studio 2008.
* Set the gpuseg project to be the startup project.
* Set the gpuseg project's working directory to be the full path of the code\gpuseg\bin folder.
* Select Build Solution from the Build menu.
* Now you can run and debug the application.

I have taken care to include all external compile-time dependencies in the SDK zip file, and always to reference them with relative paths. As a result, you should be able to follow the instructions above to build the solution with a single button click, regardless of your system configuration.

I made sure to build debug versions of 3rd party libraries with full debugging symbols whenever possible.  When stepping into a 3rd party library function (like a Qt function call for example), Visual Studio will sometimes ask where to find a particular source file.  If available, the source file is in a subfolder of the the sdk folder.  For example, the Qt source files are located in the sdk\qt folder.

In the sdk\msdev folder, I have included an install_highlighting_vs8.reg file to install Cg syntax highlighting. I have also included an autoexp.dat file to install custom visualizations of several Qt data structures in Visual Studio. Copy this file into the \Common7\Packages\Debugger subfolder of your Visual Studio installation folder to use these custom visualizers.

### Notes

* You'll need at least an NVIDIA GTX 280 to get the same performance we report in the paper.
* The binaries and code are both packaged with pre-configured project files, which are combinations of image data and meaningful parameter values. These project files are intended as an easy method of getting started with the application, and also as a way of easily reproducing the results in the paper.
* The video on the <a href='http://graphics.stanford.edu/papers/gpu_level_set/'>project page</a> offers rough guidance on the intended usage of the application.
* This codebase started as an undergraduate video game project and slowly evolved into its current form, so you will certainly find some irrelevant old systems as you dig through it.
