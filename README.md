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
- Open VirtualBox and click New. Name the new machine and choose the correct directory and ISO image. Then click Skip Unattended Installation. Choose the specs by modifying the memory and processors you give access to. We will be breaking it, so don't give it too much. I will give it 2 CPU's and 3 Gigabytes of RAM. Create a Virtual Hard disk, 50 gigabytes is fine. Press finish and start it up. (This may take a while and be tedious). Follow the instructions, click "I do not have a product key", choose "Windows 10 Pro", "Custom Installation", and let it load. Finally, follow the basic windows setup.
- Normally, computers work with three layers, the physical hardware, the operating system, and the applications. The operating system's job is to allow and control the applications to acsess the hardware. Virtual Machines in this context use what is called a type 2 hypervisor which sits on top of the host Operating System, from which a guest operating system can be run.
