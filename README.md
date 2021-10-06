# BuildrootRaspberryPi4
This is a record of building a custom OS for RaspberryPi4 using buildroot 

Buildroot is a tool used to generate embedded system operating system through cross compilation

1. Clone the buildroot repository by entering the following command
   ```bash
   git clone git://git.buildroot.net/buildroot
   ```
2. Once the cloning is done, there will be several folders in the buildroot directory. Search for "board" folder and navigate using terminal. 
   ```bash
    cd board
   ```
   ```bash
   ls 
   ```
   
   
   ![alttext](https://github.com/anikethj61/BuildrootRaspberryPi4/blob/main/cdboardls.png)


3. Ensure the board you are building the OS for exists and is being supported. 
4. Further naviagte back to ```/buildroot``` directory and make the default config file for the ```<board name>``` specific board
   ```python
   make raspberrypi4_64_defconfig
   ```
5. After the default configuration is done, its time to install extra modules necessary for implementation based on the requirement of the application. To do thi, we use the configuration menu that buildroot allows to use by entering the following command.
   ```python
   make menuconfig
   ``` 
   Select the modules and tools needed by pressing space (a star appears on the left on the selected element) and exit. A prompt pops up when exiting the menu to save the config setting, Hit Enter on Yes to save the config settings.
6. The default configuration is built and necessary tools and modules have been added. Its time to make the image by entering the following command.
   ```python
   make -j8
   ```
   This process takes time and is based on the processor of your computer. A faster processor might complete the task in 15 mins and a slower might take upto an hour. 
   
   
