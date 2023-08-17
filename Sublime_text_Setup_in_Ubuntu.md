<p align=center> <b> Install and Setup Sublime-text in Ubuntu </b></p>

1. Open a terminal window.
2. Update your package lists by running the following command:
      ```sudo apt update```
3. Install Sublime Text executing the following command:
   * Using snap:
      ```sudo snap install sublime```
   * or, Using apt(execute all the following commands one by one):
      ```
      wget -qO - https://download.sublimetext.com/sublimehq-pub.gpg | sudo apt-key add -
      sudo apt-get install apt-transport-https
      echo "deb https://download.sublimetext.com/ apt/stable/" |  sudo tee /etc/apt/sources.list.d/sublime-text.list
      sudo apt-get update  
      sudo apt install sublime-text
      ```
5. Install the C++ compiler. The C++ compiler that you will use is g++. You can install it using the following command:
      ```sudo apt install g++```
6. Create a build system for Sublime Text. A build system is a set of instructions that Sublime Text uses to compile and run your C++ code.
   You can create a build system by following these steps:
  a. Open Sublime Text.
  b. Go to Tools > Build System > New Build System.
  c. Paste the following code into the file and save it as CP.sublime-build:
```
{
 "cmd":["bash", "-c", "g++ -std=c++14 -Wall '${file}' -o '${file_path}/${file_base_name}' && timeout 0.5s '${file_path}/${file_base_name}'"],
 "file_regex": "^(..[^:]*):([0-9]+):?([0-9]+)?:? (.*)$",
 "working_dir": "${file_path}",
 "selector": "source.c, source.c++",
 "variants":
 [
   {
 	"name": "Run with C++14",
 	"cmd":["bash", "-c", "g++ -std=c++14 '${file}' -o '${file_path}/${file_base_name}' && timeout 0.5s '${file_path}/${file_base_name}' <input.txt >output.txt"]
   },
   {
 	"name": "Run with C++17",
 	"cmd": ["bash", "-c", "g++ -std=c++17 '${file}' -o '${file_path}/${file_base_name}' && timeout 0.5s '${file_path}/${file_base_name}' <input.txt >output.txt"]

  }
 ]
}
```
6.  Changing layout for I/O operations:
  * From the top menu, select View->Layout->Columns :3 or press Shift+Alt+3.
  * Now select View->Groups->Max columns: 2.
  * Add input.txt in top-right and output.txt in bottom-right.
  * Now add your <File_Name>.cpp file in the left column and (compile + run) using the shortcut ctrl+B.

<p align=center> >>>ENJOY COMPETITIVE PROGRAMMING<<< </p>

