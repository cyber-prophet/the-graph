title:: cyber-prophet extra 1: installing mac from 0

- Software installation
	- https://brew.sh/
		- ```/bin/bash -c "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/HEAD/install.sh)"
		  ```
		- ![image.png](../assets/image_1665918154752_0.png)
		- Check that brew installed with `brew help` command
	- Go compile
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
	- Checking if cyber is installed correctly
		- `cyber version`
	- So we found that we need to add `~/go/bin` path to $PATH variable
		-
	-