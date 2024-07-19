# System Info Unique ID
- The goal here is to create a unique ID for any computer
	- If I run this application on my machine, it will always have the same ID
	- If I run this application on another machine, its ID will always be the same, but different than the ID on the other machine
## Bash Approach
- With bash I can a ton of information about my system, because of that, I collected a good amount, and made an ID
- The system information I used were: 
	- KERNEL_INFO
	- CPU_INFO
	- RAM_COUNT
	- HOSTNAME
	- SYSTEM_UUID
	- BIOS_INFO
- With the system information fetched in bash, I then hashed it with sha256, and gave it to the user
## C Approach
- In C I fetched the Machine-id.txt & Machine-info.txt files located in /etc
- I then take the content from these files and set them to a seed which then creates a randomized ID with numbers and letters
- Default size is 32, but that can be adjusted with the -s or --size flags
## To Run Bash
- To run the bash approach run the command
```bash
sudo ./Bash/SysInfo
```
- Sudo is needed for the BIOS info
- You then will be given a unique ID
## To Run C
- I created a Makefile that will run the gcc command
```bash
cd ./C
make
./GenerateID
```
