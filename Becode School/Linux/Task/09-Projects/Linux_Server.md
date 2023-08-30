
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
     - 
### Step 2: Configure the Master DNS Server

#### On Ubuntu

1. Open the terminal and create the forward zone file:

```bash
sudo cp /etc/bind/db.local /etc/bind/forward.computingforgeeks.local.db
sudo vim /etc/bind/forward.computingforgeeks.local.db
```

**Explanation:** The first command copies the sample zone lookup file, and the second command opens it for editing.

2. Modify the forward zone file:

```text
$TTL    604800
@       IN      SOA     ns1.computingforgeeks.local. root.ns1.computingforgeeks.local. (
                              3         ; Serial
                         604800         ; Refresh
                          86400         ; Retry
                        2419200         ; Expire
                         604800 )       ; Negative Cache TTL

;Name Server Information
@        IN      NS      ns1.computingforgeeks.local.

;IP address of Name Server
ns1     IN      A       192.168.1.12

;Mail Exchanger
computingforgeeks.local.   IN     MX   10   mail.computingforgeeks.local.

;A – Record HostName To IP Address
www     IN       A      192.168.1.13
mail    IN       A      192.168.1.14

;CNAME record
ftp     IN      CNAME   www.computingforgeeks.local.
```

**Explanation:** This configuration file sets up the forward zone for the "computingforgeeks.local" domain, specifying the name server, mail exchanger, A records, and CNAME record.

3. Save and exit the file.

4. Create the reverse zone file:

```bash
sudo cp /etc/bind/db.127 /etc/bind/reverse.computingforgeeks.local.db
sudo vim /etc/bind/reverse.computingforgeeks.local.db
```

**Explanation:** The first command copies the sample reverse zone file, and the second command opens it for editing.

5. Modify the reverse zone file:

```text
$TTL    604800
@       IN      SOA     computingforgeeks.local. root.computingforgeeks.local. (
                              3         ; Serial
                         604800         ; Refresh
                          86400         ; Retry
                        2419200         ; Expire
                         604800 )       ; Negative Cache TTL

;Name Server Information
@       IN      NS     ns1.computingforgeeks.local.
ns1     IN      A       192.168.1.12

;Reverse lookup for Name Server
12      IN      PTR    ns1.computingforgeeks.local.

;PTR Record IP address to HostName
13     IN

      PTR    www.computingforgeeks.local.
14     IN      PTR    mail.computingforgeeks.local.
```

**Explanation:** This configuration file sets up the reverse zone for the "computingforgeeks.local" domain, specifying the name server, PTR records for IP addresses, and reverse lookup for the name server.

6. Save and exit the file.
2. Modify the DHCP configuration file:

```text
subnet 192.168.1.0 netmask 255.255.255.0 {
  range 192.168.1.100 192.168.1.200;
  option routers 192.168.1.1;
  option domain-name-servers 192.168.1.12;
  option domain-name "computingforgeeks.local";
  option broadcast-address 192.168.1.255;
  default-lease-time 600;
  max-lease-time 7200;
}

```

**Explanation:** This configuration file sets up the DHCP subnet, IP range, router, DNS server, domain name, and lease times.

3. Save and exit the file.

4. Restart the DHCP service:

```bash
sudo systemctl restart isc-dhcp-server
```
     ```
To create a sample HTML page and verify the HTTP server is working, follow these steps:

1. Open a terminal or command prompt.

2. Execute the following commands:
   ```bash
   sudo su
   echo "Hello, World!" > /var/www/html/index.html
   exit
   ```

   The first command (`sudo su`) switches to the root user to gain necessary permissions. The second command creates an HTML file named `index.html` in the `/var/www/html` directory and writes the content "Hello, World!" into it. The third command (`exit`) exits the root user session.

3. Open a web browser on the workstation.

4. Enter the server's IP address in the browser's address bar. For example, if the server's IP address is 192.168.1.1, enter `http://192.168.1.1`.

5. Press Enter to load the web page.

If the HTTP server is working correctly, you should see the text "Hello, World!" displayed in the web browser. This confirms that the server is successfully serving the HTML page.
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

## Step-by-Step Guide: Setting up a DNS Server with BIND on Ubuntu and Kali Linux

### Prerequisites
- Ubuntu and Kali Linux installed in VirtualBox.
- Ubuntu IP Address: 192.168.1.12
- Kali Linux IP Address: 192.168.1.13
- Subnet Mask: 255.255.255.0

### Step 1: Install BIND DNS Server

On both Ubuntu and Kali Linux, open the terminal and execute the following commands:

```bash
sudo apt update -y
sudo apt install -y bind9 bind9utils bind9-doc dnsutils
```

**Explanation:** These commands update the package repositories and install the BIND DNS server and its utilities.



7. Edit the main BIND configuration file:

```bash
sudo vim /etc/bind/named.conf.local
```

8. Add the following lines at the end of the file:

```text
zone "computingforgeeks.local" {
    type master;
    file "/etc/bind/forward.computingforgeeks.local.db";
};

zone "1.168.192.in-addr.arpa" {
    type master;
    file "/etc/bind/reverse.computingforgeeks.local.db";
};
```

**Explanation:** These lines specify the zones and their corresponding configuration files.

9. Save and exit the file.

10. Restart the BIND service:

```bash
sudo systemctl restart bind9
```

#### On Kali Linux

Repeat Steps 2.1 to 2.10 from the Ubuntu configuration.

### Step 3: Configure DHCP

#### On Ubuntu

1. Edit the DHCP configuration file:

```bash
sudo vim /etc/dhcp/dhcpd.conf
```



#### On Kali Linux

Repeat Steps 3.1 to 3.4 from the Ubuntu configuration.

### Step 4: Test the DNS Server

1. On both Ubuntu and Kali Linux, open the terminal and install `dnsutils`:

```bash
sudo apt install -y dnsutils
```

2. Verify the DNS resolution by executing the following commands:

```bash
nslookup www.computingforgeeks.local
nslookup 192.168.1.12
```

**Explanation:** These commands check the DNS resolution for the configured domain name and IP address.

---

Please note that while this guide provides detailed steps for setting up a DNS server with BIND, there may be slight variations depending on the specific versions of Ubuntu, Kali Linux, and BIND DNS server that you are using. Make sure to adapt the commands and configurations if needed.

I hope this guide helps you in setting up your DNS server. Let me know if you have any further questions!
