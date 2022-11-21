## Commands from video.
	- ### In Power Shell of Windows:
		- ```
		  wsl --install
		  wsl --set-default-version 1
		  wsl --install -d Ubuntu
		  ```
	- ### In console of Ubuntu:
		- ```
		  wget https://go.dev/dl/go1.19.1.linux-arm64.tar.gz
		  export PATH=$PATH:/usr/local/go/bin
		  sudo tar -C /usr/local -xzf go1.19.1.linux-arm64.tar.gz
		  sudo apt-get install build-essential
		  make install CUDA_ENABLED=false LEDGER_ENABLED=false
		  export PATH=$PATH:/home/uuser/go/bin # dont forget to change the uuser name to yours accordingly
		  ```
	- ### Testing cyber
		- ```
		  cyber version
		  
		  cyber q bank total  --chain-id bostrom --node https://rpc.bostrom.cybernode.ai:443
		  ```