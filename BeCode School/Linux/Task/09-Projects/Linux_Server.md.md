

## Linux Network Services Setup using Virtual Machines (without GUI)

### Server Configuration (Ubuntu):

1. Create a new virtual machine in VirtualBox named "Ubuntu Server" without a GUI (choose the Ubuntu Server ISO).
   - A virtual machine is like a computer inside your computer. We will use it to run Ubuntu, a Linux operating system.
   - The ISO file is a disk image of the Ubuntu installation media.
2. Allocate appropriate resources (e.g., CPU, memory) based on your system capabilities.
   - We need to assign enough resources to ensure Ubuntu runs smoothly on the virtual machine.
3. Configure the network adapter for internal network mode:
   - In VirtualBox, go to the settings of the virtual machine.
   - Under the "Network" tab, select "Internal Network" from the drop-down menu.
   - Set the name of the internal network to "library_internal_net" (or any other suitable name).
   - This network mode allows the virtual machine to communicate with other virtual machines but not with the outside world.
4. Start the virtual machine and install Ubuntu Server using the ISO file.
   - Ubuntu Server is a version of Ubuntu designed for running servers.
5. During the installation process, choose the minimal installation option without a GUI.
   - The GUI (Graphical User Interface) provides a visual interface, but we don't need it for a server.
6. Configure the network settings:
   - When prompted, select "Configure network manually."
   - with virtual box make sure to select internal network
   - Set the IP address to `192.168.1.1`.
     - IP address is like a unique identifier for devices on a network. We will use this address to access the server.
   - Set the subnet mask to `255.255.255.0`.
     - Subnet mask determines which part of the IP address identifies the network and which part identifies the specific device.
   - Leave the gateway and DNS fields blank for now. We will configure them later.
   - Complete the installation process.

### Additional Configuration Steps (Server - Ubuntu):

1. Install the required services:
   - Open the terminal (command prompt-like interface) on Ubuntu.
   - Execute the following commands one by one:

     ```bash
     sudo apt update
     sudo apt install isc-dhcp-server bind9 mariadb-server
     ```

     - The `apt` command is used to manage software packages in Ubuntu. We use it to install the required services.

2. Configure the DHCP service:
   - Open the DHCP configuration file using a text editor:

     ```bash
     sudo nano /etc/dhcp/dhcpd.conf
     ```

   - Add the following lines at the end of the file:

     ```bash
     subnet 192.168.1.0 netmask 255.255.255.0 {
       range 192.168.1.100 192.168.1.200;
       option routers 192.168.1.1;
     }
     ```

3. Configure the DNS service:
   - Open the BIND configuration file using a text editor:

     ```bash
     sudo nano /etc/bind/named.conf.options
     ```

   - Uncomment the following lines by removing the `//` at the beginning:

     ```bash
     forwarders {
       8.8.8.8;
       8.8.4.4;
     };
     ```

4. Configure the web server and MariaDB:
   - Execute the following commands one by one:

     ```bash
     sudo apt install apache2
     sudo systemctl enable apache2
     sudo apt install php libapache2-mod-php mariadb-client
     sudo systemctl enable mariadb
     ```

5

. Create a weekly backup script:
   - Execute the following command to create a new backup script file:

     ```bash
     sudo nano /usr/local/bin/backup.sh
     ```

   - Add the following lines to the file:

     ```bash
     #!/bin/bash
     BACKUP_DIR="/backup"
     ARCHIVE_NAME="server_config_backup_$(date +%Y%m%d).tar.gz"
     CONFIG_DIR="/etc"
     tar -zcvf "$BACKUP_DIR/$ARCHIVE_NAME" "$CONFIG_DIR"
     ```

6. Make the script executable:
   - Execute the following command:

     ```bash
     sudo chmod +x /usr/local/bin/backup.sh
     ```

7. Configure remote management (SSH):
   - Install the OpenSSH server by executing the following command:

     ```bash
     sudo apt install openssh-server
     ```

8. Configure the firewall to allow necessary services:
   - Execute the following commands one by one:

     ```bash
     sudo ufw allow 22/tcp
     sudo ufw allow 53/tcp
     sudo ufw allow 80/tcp
     sudo ufw enable
     ```

### Workstation Configuration (Kali Linux):

1. Create another virtual machine in VirtualBox named "Kali Linux" without a GUI (choose the Kali Linux ISO).
   - Kali Linux is a specialized Linux distribution for penetration testing and security auditing.
   - Repeat the steps mentioned earlier to allocate resources and configure the network adapter in internal network mode.
2. Start the virtual machine and install Kali Linux using the ISO file.
   - During the installation, choose the minimal installation option without a GUI.
   - Configure the network settings as mentioned earlier for the server but use the IP address `192.168.1.2`.
     - The IP address must be different from the server's IP address.
3. Once the installation is complete, open the terminal on Kali Linux.

### Additional Configuration Steps (Workstation - Kali Linux):

1. Install the required applications:
   - Execute the following command to install LibreOffice, GIMP, and the Mullvad browser:

     ```bash
     sudo apt update
     sudo apt install libreoffice gimp mullvad
     ```

2. Configure automatic addressing:
   - By default, Kali Linux uses DHCP for automatic addressing.
   - It means the workstation will automatically obtain an IP address from the server when connected to the internal network.
3. Configure separate partition for /home folder (optional):
   - This step requires advanced disk partitioning knowledge, and it's optional for the demonstration.


---
