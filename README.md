ofxMSAOpenCL
=====================================

Introduction
------------
ofxMSAOpenCL is an easy-to-use C++ openFrameworks add-on for OpenCL wrappers. All underlying openCL objects are accessible and allow advanced features.
Demo (1M particles @ 100-200 fps) at [vimeo.com/7332496](http://vimeo.com/7332496)

License
-------
This source code is licensed under the [MIT License](https://secure.wikimedia.org/wikipedia/en/wiki/Mit_license).  
Copyright (c) 2008-2012 Memo Akten, [www.memo.tv](http://www.memo.tv)  
The Mega Super Awesome Visuals Company


Installation
------------
Copy this project to your openFrameworks/add-ons folder.

For issues relating to graphics cards and usage of Software Development Kit 10.8 with OpenCL, install the following drivers available at: www.nvidia.com/object/cuda-mac-driver.html

Dependencies
------------

* [ofxMSAPingPing]{https://github.com/memo/ofxMSAPingPong}

### Windows / NVidia

* CUDA SDK [https://developer.nvidia.com/cuda-downloads]

### Examples

Some examples also require [ofxMSATimer]{https://github.com/memo/ofxMSATimer}

Compatibility
------------
openFrameworks 0072  
I am generally testing only with [openFrameworks](www.openframeworks.cc), however it should work with [Cinder](www.libcinder.org) too. If it doesn't, please file an issue.


Known issues
------------
none

Version history
------------
### v2.1    23/09/2012
- compatible with OF0072
- renamed (uppercase) MSA namespace to (lowercase) msa. (kept MSA as an alias for backwards compatibility)
- no longer requires MSACore

### v2.0
- move to centralized MSALibs (requires MSACore)
- everything is MSA:: namespace

### v0.3
- added image support
- restructured buffer/memory management
- minor break in backwards compatability: createBuffer returns ofxOpenCLBuffer instead of cl_mem. so
   - writeBuffer and readBuffer are methods of ofxOpenCLBuffer, not ofxOpenCL
   - when passing buffer (or image) as parameter to ofxOpenCLKernel::setArg, use ofxOpenCLBuffer::getMemoryObject() (which returns the cl_mem)

### v0.2
- added support for multiple devices
- sharing context with opengl (only on mac osx at the moment)
- better handling of multi-dimensional data (minor backwards compatability break with kernel::run)
- support for opengl/opencl buffer+texture sharing 
- can load programs from binary (support for creating binary coming soon)


### v0.1
- initial version

