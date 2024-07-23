## Windows Terminal, WSL2, Kali, ZSH and P10K

This article is a "How To" for setting up Windows Subsystem for Linux (WSL), to run latest Kali distro with customized colors and themes on "Windows Terminal" for *Windows 10 OS Build 20H1 and above.* 

If needed, see this Wikipedia article on ["Windows Update History"](https://en.wikipedia.org/wiki/Windows_10_version_history) to learn about Windows OS Builds.

### Windows Terminal and WSL2

On Windows 10 OS with Build greater than 1909, WSL2 can be installed and operated for instantly creating virtual machines that run a Linux distribution. 

On my computer, the BIOS is called UEFI (Unified Extensible Firmware Interface) and it does not have any option for memory virtualization. Instead, Windows Hypervisor is enabled via Windows Features or while installing WSL. 

- **Step 1:** Get the Open Source "Windows Terminal" from Microsoft Store

    - Press the *Windows Key* along with *s* on your keyboard to open Search option. Type "Store" and open the Microsoft Store.
	
	- Search for "Windows Terminal" and install it. 

- **Step 2:** Install WSL without any Linux distro

    - Open Windows Terminal in "Run as Administrator" mode. For this, find the icon for the Windows Terminal app in the *Start Menu* and right-click on the icon for options, then click on "Run as Administrator." 
	
	- Next, type the following commands in the terminal: 
	
		```shell
		wsl --install --no-distribution  
	
		wsl --update  
		```
	
	The above set of commands performed the required operation for installing WSL2 and enabling memory virtualization for my computer. Other commands related to WSL can be found using `wsl --help` option. 
	
### Kali

- **Step 3:** Install Kali 

	- The command, `wsl --list --online` will show the available distros
	
	- Install Kali using the command: 
	
		```shell
		wsl --install --kali-linux  
		```

- **Step 4:** Open a Kali Profile in Windows Terminal 

	- The downward arrow sign on the *Top Bar* of the Windows Terminal will give options for opening a new tab, in which Kali should now be available; click on it. 
	
	- On running Kali for the first time, you will be asked to create a username along with its sudo password; create them when prompted. 
	
- **Step 5:** Update Kali

	- After being signed in with your username in the Kali profile of Windows Terminal, type the following command:
	
		```shell
		sudo apt update  
		```
		
	- Following that you can try the command: 
	
		```shell
		sudo apt upgrade  
		```
		
Your Windows Start Menu will now have an icon for launching minimal installation of Kali with BASH in a terminal window. We will now download and install ZSH in the next step for Kali in Windows Terminal. 

### ZSH 

The ZSH profile and screen prompt can be extensively customized via settings of Windows Terminal GUI and community maintained modules. It makes working with headless virtual machines easier, and one can become proficient in using keyboard shortcuts to do various scripting and coding projects without a mouse, from the ZSH command line. Navigating different file systems of different machines while managing Continuous Integration and Deployment projects via Git can become a breeze. 

- **Step 6:** Type the following command in Kali BASH to download and install ZSH:
	
	```shell 
		sudo apt install zsh -y
	```

#### Oh-My-ZSH 

- **Step 7:** Use the Oh-My-ZSH extension 

	- To switch the default command line shell in Kali from BASH to ZSH use the following installation Shell Script from the Oh-My-ZSH project: 
	
		```shell 
		sh -c "$(curl -fsSL https://raw.github.com/ohmyzsh/ohmyzsh/master/tools/install.sh)"
		```

	- When prompted to switch to ZSH as default shell, press `Y` to indicate Yes, and hit Enter, and then follow the prompts. 

The minimalist form of ZSH would now be available in Kali by default. 

#### Nerd Fonts

At this point, some of the fonts rendered in ZSH via Windows Terminal's engine might be garbled or displayed with incorrect glyphs. After trying many fonts like Cascadia, DroidMono, Meslow, UbuntuSans, etc. along with numerous changes to the "Kali Profile" within the Windows Terminal's Settings, only the following worked: 

- **Step 8:** Download FiraMono font face from Nerd Fonts, 

	- Install "FiraMono Nerd Font" or "FiraMono Nerd Font Mono" using the instructions provided in the Nerd Fonts documentation: 

    - https://github.com/ryanoasis/nerd-fonts?tab=readme-ov-file#font-installation

	- Or view the following video from Christian Lempa at 2 min 25 sec, on how to install fonts in Windows machine. 

		- Make your WSL or WSL2 terminal awesome - https://www.youtube.com/watch?v=235G6X5EAvM

The latest version of Windows Terminal allows for customization of fonts for each available profile. To change the way Fonts are rendered within the Kali profile in Windows Terminal's Settings: 

- Click the downward arrow in the Top Bar of the terminal window (or press `Ctrl+,`) to get menu for Settings.

- On the left-hand side, of the settings menu, scroll down till you see the option for "kali-linux", and click on it.

- Next, scroll down on the options available on the right-hand side, under subheading of "Additional settings", click on "Appearance" 

	- Choose the "Color scheme" you like.
	
	- Choose the "Font face" from the drop-down menu as FiraMono. If it is not visible in the drop-down menu click on the checkbox for "Show all fonts." 
	
- Next, go back to "kali-linux" profile settings, and under subheading of "Additional settings", click on "Advanced"

	- Change the "Text antialiasing" method to "ClearType" from "GrayScale".
	
	- Keep the "Use the new text renderer ('AtlasEngine')" to `on` position. 


### Powerlevel10K

Finally, to beautify and prettify ZSH, the P10K extension can be used. 

- **Step 9:** Download and install Powerlevel10K: 

	```shell
	git clone --depth=1 https://github.com/romkatv/powerlevel10k.git ${ZSH_CUSTOM:-~/.oh-my-zsh/custom}/themes/powerlevel10k
	```

	- Edit the `~/.zshrc` file using Nano or Vim or your preferred text editor. Change the value of `ZSH_THEME="robbyrussel"` to `ZSH_THEME="powerlevel10k/powerlevel10k"`

	- Save the changes made to `.zshrc` file and close the terminal app. Reopen the Windows Terminal and open the Kali profile. You will be prompted to create the configuration file for P10K via a series of questions. Have a look at the "DevInsideYou" video linked in the Reference section to understand what each of those questions eventually do. 

- **Step 10:** Edit the `~/.p10k.zsh` file manually, as and when required: 

	- See video on P10K customization by DevInsideYou - https://www.youtube.com/watch?v=OjxmqRcSWMQ&t=2267s 

	- For example, manually editing the `PS1` environment variable of a command line shell and saving it to `.zshrc` can be tedious and painful. So, to have an information segment such as `username@hostmachine` displayed at all times at the shell command line prompt:
	
		- Paste the line for `context` in `.p10k.zsh` where required, either under `POWERLEVEL9K_LEFT_PROMPT_ELEMENTS` or `POWERLEVEL9K_RIGHT_PROMPT_ELEMENTS`
		
		- And comment out the line for `typeset -g POWERLEVEL9K_CONTEXT_{DEFAUL,SUDO}_{CONTEXT,VISUAL_IDENTIFIER}_EXTENSION=`

You can now have a clean and nice looking interface for the command line shell with useful information displayed where you need it most. Other options for plugins and customization are conveniently done through Oh-My-ZSH.  

Happy scripting and coding!

Cheers!

<br>

### Reference

- Christian Lempa

	- YouTube Video - [Make your WSL or WSL2 terminal awesome - with Windows Terminal, zsh, oh-my-zsh and Powerlevel10k](https://www.youtube.com/watch?v=235G6X5EAvM&t=300s), 2020-07-05. 
	
	- Documentation of codes used in the video - https://github.com/christianlempa/videos/tree/main/windows-terminal-powerlevel10k

- DevInsideYou
	- YouTube Video - [The Ultimate #p10k Tutorial #zsh #alacritty #byobu #FiraCode](https://www.youtube.com/watch?v=OjxmqRcSWMQ), 2022-09-25. 
	
- Ryan Oasis, Nerd Fonts 

	- Overview and introduction - https://github.com/ryanoasis/nerd-fonts?tab=readme-ov-file#---1
	
	- Get FiraMono.zip from - https://github.com/ryanoasis/nerd-fonts/releases/tag/v3.2.1

- NetworkChuck

	- YouTube Video - [Linux on Windows......Windows on Linux](https://www.youtube.com/watch?v=vxTW22y8zV8), 2024-07-03. 
	
	- YouTube Video - [Kali Linux APPS on Windows in 5min (WSLg)](https://www.youtube.com/watch?v=27Wn921q_BQ), 2022-03-04. 

