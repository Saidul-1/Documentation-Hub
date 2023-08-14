# ModelSim Installation on Ubuntu

### Installation requirements

The free version of Modelsim is a 32-bit binary and therefore requires certain 32-bit libraries in order to work correctly. For Ubunutu, execute the following commands in terminal one by one and install the packages

```sh
sudo dpkg --add-architecture i386
sudo apt-get update
sudo apt-get install libc6:i386 libncurses5:i386 libstdc++6:i386 lib32ncurses6 libxft2 libxft2:i386 libxext6 libxext6:i386 
```

### Installation

* [Download](https://download.altera.com/akdlm/software/acdsinst/20.1std.1/720/ib_installers/ModelSimSetup-20.1.1.720-linux.run) the ModelSim - Intel FPGA edition installer. 

* Open the folder/directory where the installer file has been downloaded

* Make the installer executable

```sh
chmod +x ModelSimSetup-20.1.1.720-linux.run
```

* Run the installer and install ModelSim:

```sh
./ModelSimSetup-20.1.1.720-linux.run
```

We assume ModelSim to be installed to `/opt`. If this is the case, the binaries are in `/opt/modelsim_ase/bin/`. In order to work with these tools, you need to add this folder to the path variable. Therefore, add the following line to your terminal configuration file, e.g., `.bashrc` or `.zshrc` by executing the command in terminal.

```sh
export PATH=$PATH:/opt/modelsim_ase/bin
```
<br> <b> ModelSim has been Installed! </b>
### Run ModelSim
Now, you can run ModelSim executing the following command in terminal from any directory
  ```sh
  ./intelFPGA/20.1/modelsim_ase/bin/vsim
  ```
  Or, go to the following directory ``` intelFPGA/20.1/modelsim_ase/bin/ ```. select the file 'vsim' and run it as a program from the right-click menu. 

