# Section 3: Understanding Docker

- Introduction: Virtual machines (VMs) and Docker containers are distinct technologies for deploying and running software applications, each with its own benefits and use cases. Below are the main differences between them

- Architecture: VMs simulate a full operating system (OS) and run on a hypervisor, which abstracts the hardware. Each VM needs its own OS and resources, leading to significant overhead. Conversely, Docker containers are isolated user-space environments sharing the OS kernel with the host, resulting in lower resource usage.

- Portability: VMs are generally less portable than Docker containers because they require an entire OS installation and setup, which can be complex and time-consuming. Docker containers are lightweight and portable, containing all dependencies and configurations within a single image that can run on any Docker-supported machine.
