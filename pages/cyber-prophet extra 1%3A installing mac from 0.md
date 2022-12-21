title:: cyber-prophet extra 1: installing mac from 0

- Software installation
	- https://brew.sh/
		- ```
		  /bin/bash -c "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/HEAD/install.sh)"
		  ```
		- ![image.png](../assets/image_1665918154752_0.png){:height 507, :width 706}
		- Check that brew installed with `brew help` command
	- Go compiler
		- `brew install go`
	- Git
		- `brew install git`
	- Visual Studio Code
		- `brew install --cask visual-studio-code`
- Building cyber
	- Creating new directory
		- `mkdir gitfolder`
		- `cd gitfolder`
	- Clonning repository
		- `git clone https://github.com/cybercongress/go-cyber.git`
		- `cd go-cyber`
		- `make install`
	- Checking if cyber is installed correctly
		- `cyber version`
	- So we found that we need to add `~/go/bin` path to $PATH variable
		- `pwd`
		- `export PATH=$PATH:/Users/uuser/go/bin`
			- ```
			  > cyber version
			  0.3.2
			  ```
- Installing nushell
	- `brew install nushell`
- Launching nu
	- `nu`
- Installing Alacritty terminal
	- `brew install --cask alacritty`
	- To open the application 'Alacritty' for the first time - click on it's icon with right click and choose the 'open' button
		-
- Configurate Alacritty
	- goals
		- to use nushell as default shell
		- to change the size of fonts
- Download `alacritty.yml` from: https://github.com/alacritty/alacritty/releases/latest
	- move the config file into home folder `mv alacritty.yml ~/.alacritty.yml`
	- open the yml file in vs code: `code ~/.alacritty.yml`
- In VS Code in `.alacritty.yml`:
	- line 26
		- `window:`
	- line 81
		- `startup_mode: Maximized`
	- line 111
		- `font:`
	- line 159
		- `size: 18.0`
	- find in terminal the path to nu: `which nu`
	- line 436 - To make nushell default shell for Alacritty
		- ```
		  shell:
		   program: /opt/homebrew/bin/nu
		   args:
		     - --login
		  ```
		-
- Configuring nu in Alacritty to enable open nushell:
	- adding go executable folder into $PATH variable
		- `let-env PATH = ( $env.PATH | append /Users/uuser/go/bin )`
	- check if cyber works
		- `cyber version`
	- Add this command into config of nu
		- `config env`
			- add into the last line
			- Intel mac
				- ```
				  let-env PATH = ( $env.PATH | append [
				          /Users/uuser/go/bin
				          /usr/local/bin
				          /usr/local/sbin
				          ]
				  )
				  ```
			- ARM mac (m1, m2 processors)
				- ```
				  let-env PATH = ( $env.PATH | append [
				  	/Users/uuser/go/bin  
				  	/opt/homebrew/bin  				# beware that for intel mac this path is diffrent
				  	/opt/homebrew/sbin 
				  	] 
				  )
				  ```
				- Modify this command to add Brew folders into $PATH variable to. Beware of the name of your user. In the video it is 'uuser', but in your case it is likely to be different
	- restart alacritty
	- check if your $PATH variable looks correctly
		- `echo $env.PATH`
		- ![image.png](../assets/image_1665923863696_0.png)
- Install Starship to make our promt look beautiful
	- ![image.png](../assets/image_1665923942928_0.png)
	- `brew install starship`
	- `config env`
		- append this lines to the end
			- ```
			  mkdir ~/.cache/starship
			  starship init nu | sed "s/size -c/size/" | save ~/.cache/starship/init.nu` --force
			  ```
	- config nu
		- append this line to the end:
			- `source ~/.cache/starship/init.nu`
- Install NERD font for Starship
	- `brew tap homebrew/cask-fonts`
	- `brew install --cask font-jetbrains-mono-nerd-font`
		- Old verison
		  collapsed:: true
			- `brew install --cask font-go-mono-nerd-font`
	- In Alacritty in `.alacritty.yml`:
		- line 120
			- `family: JetBrainsMono Nerd Font`
			- Old version
			  collapsed:: true
				- `family: GoMono Nerd Font Mono`
- Install pussy
	- `git clone https://github.com/joinresistance/space-pussy.git`
	- `cd space-pussy`
	- `make install`
	- Check if it works
		- `pussy version`
- Install IPFS
	- `brew install ipfs`
	-
-