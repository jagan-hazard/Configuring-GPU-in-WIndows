# Configuring-GPU-in-WIndows

GPU: NVIDIA GEFORCE-GTX TITAN X (uses PASCAL architecture with 3584 NVIDIA CUDA cores)

Minimum Requirements of GPU:
----------------------------

        1. Power supply of 600W or more having one 6-pin and one 8-pin connector [RM750X-Corsair]
        2. Windows 7 OS or higher
        3. System RAM memory 16 GB (minimum 16 GB)
        4. Motherboard- PCI 16x Expressslot (PCI 16x Express Cable if the GPU cannot be connected to CPU directly)
 (Note: Proper Internet Connection is required for GPU driver installation)
 
Steps for Connection
--------------------

  Here we are using seperate SMPS for CPU and GPU, if that is the case use this step or else skip this step
  
        1. Connect the cable from male PCI slot of GPU to female PCI slot of motherboard
        2. Connect 6 and 8-pin connector to GPU, from 6+2 PCI-e slot of SMPS
        3. Connect 24-pin ATX cable to SMPS and its other end is short using jumper wire at pin-16 and pin-17(pin-15 and pin-16 can                 also be used). For pin details refer the pin diagram in the diagram below.
        
  (Note: Switch on CPU and SMPS in parallel. Since, GPU is connected to SMPS.)
  
 NVIDIA Driver Installation
 --------------------------
        1. Connect the GPU to the system.
        2. DownloadGeForce Experience from the NVIDIA website.
        3. Create a login to get the file.
        4. A downloadable NVIDIA driver is available and used for installation.
   (Note: Steps 1, 2 and 3 will only work, if GPUconnected to the system)
   
 CUDA Toolkit Installation
 --------------------------
        1) Download and install CUDA toolkit (version 9.0 is used—this supports keras) from the website                                             https://developer.nvidia.com/cuda-toolkit. From that link install the Base Installer first followed by batch files if any.
        2) Download cuDNN. To download this package, NVIDIA developer login is required(login access is free). Deep learning SDK-->                 Deep Learning Primitives (cuDNN)-->Download cuDNN-->Agree to terms and conditions--> Download the cuDNN that matches CUDA               9.0
        3) Extract the cuDNN folder. cuDNN contains three folders i.e., bin, include and lib.
        4) Copy the 'cudnn64_7.dll' file in 'bin' folder from E:\gpu related software\cudnn-9.0-windows7-x64-v7.1\cuda\bin to                      C:\Program Files\NVIDIA GPU Computing Toolkit\CUDA\v9.0\bin 
        5) Copy the 'cudnn.h' file in 'include' folder from E:\gpu related software\cudnn-9.0-windows7-x64-v7.1\cuda\include to                     C:\Program Files\NVIDIA GPU Computing Toolkit\CUDA\v9.0\include 
        6) Copy the 'cudnn.lib' file in 'lib' folder from E:\gpu related software\cudnn-9.0-windows7-x64-v7.1\cuda\lib\x64 to                       C:\Program Files\NVIDIA GPU Computing Toolkit\CUDA\v9.0\lib
        
  Upto to this GPU is configured with the OS. 
  
  # Installing CPU and GPU supported version of Tensorflow in seperate environment.
  
  Software Installation of Anaconda
  ---------------------------------
  Download and install Anaconda 3. In anaconda, several environments can be created.GPU related packages are installed after creating another environment
  
  CPU supported installation: (In Base environment)
  -------------------------------------------------
  
  The following steps can be done in an anaconda command prompt
            
            1) Installing keras:
                     pip install keras 
            To check if keras is working, type ‘python’ in command prompt and type ‘import keras’
            
            2) Installing tensorflow:
                    pip install tensorflow 
            To check if tensorflow is working, type ‘python’ in command prompt and type ‘import keras’
            
            3) Installing opencv:
                    conda install –c conda-forge opencv 
            To check opencv installation, type ‘python’ in command prompt and type
                  >>import cv2
                  >>cv2.__version__
  
 Creating Environment in anaconda
 --------------------------------
            1) Create environment using the following command
                    conda create –n (name) pip python=3.5 
                eg. If name of the environment is ‘gpu’, conda create –n gpu pip python=3.5
            
            2) To activate the environment, type ‘activate (name)’ in anaconda command prompt
            
            3) To deactivate the environment, type ‘deactivate’ 
 
 GPU supported Installation:
 ---------------------------
 
 Assuming the new environment created is ‘gpu’ the following steps are carried out.
 
            1) Activate the environment
                    activate gpu
            
            2) Installing keras:
                    pip install keras 
              To check if keras is working, type ‘python’ in command prompt and type ‘import keras’
            
            3) Installing tensorflow for gpu:
                    pip install tensorflow-gpu 
              To check if tensorflow is working, type ‘python’ in command prompt and type ‘import keras’
            
            4) Installing opencv:
                    conda install –c conda-forge opencv 
              To check opencv installation, type ‘python’ in command prompt and type 
                  >>import cv2 
                  >>cv2.__version__
   
   Note: Since, already the packages are installed, ‘pip install –ignore-installed (package name)’ should be used, if it says  ‘Requirement already satisfied’. All necessary packages have to be installed again for working in the new environment created.
   
  
