# installation

Ubuntu 14.04 with TITAN X Maxwell deep learning installation (CUDA7.5 + cuDNN 5.1)

Install Git:

     sudo apt-get install git
    
1, install NVIDIA driver
--------------
* Find your graphics card model:

     lspci | grep -i nvidia
     
* Add the "Proprietary GPU Drivers" PPA repository:

        sudo add-apt-repository ppa:graphics-drivers/ppa
        
* find the latest driver version compatible with your graphics card.

* Update the repositories database:

        sudo apt-get update
        
* Install your selected version of the graphics card (this could break your graphic system, be sure to know how to use a shell to be able to repair it), for example:

        sudo apt-get install nvidia-375
        
* Restart your system:

        sudo shutdown -r now
        
* Check the NVIDIA drivers installed:

        cat /proc/driver/nvidia/version      
        
2, install CUDA
---------
* Check that your computer is CUDA enabled (you should have a compatible NVIDIA graphics card):

        lspci | grep -i nvidia
        
* You need to have an account or register in the NVIDIA developer program (it's free): <https://developer.nvidia.com/user>
* Download CUDA 7 from: <https://developer.nvidia.com/cuda-downloads>, you can download the "deb (network)" package (cuda repo).
* Go to the downloads directory:

        cd ~/Downloads
        
* Install the package (the repository):

        sudo dpkg -i cuda-repo-ubuntu1404*amd64.deb

* Update the repositories DB:

        sudo apt-get update

* Install CUDA (it should list cuda packages):

        sudo apt-get install cuda

* Add CUDA to the PATH variable (and make it permanent for the current user):

        echo 'export PATH=/usr/local/cuda/bin:$PATH' >> ~/.bashrc

* Add CUDA to the LD_LIBRARY_PATH variable (and make it permanent for the current user):

        echo 'export LD_LIBRARY_PATH=/usr/local/cuda/lib64:$LD_LIBRARY_PATH' >> ~/.bashrc
        
