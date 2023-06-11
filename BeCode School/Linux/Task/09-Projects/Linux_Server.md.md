

Certainly! Here's a more detailed step-by-step guidance for setting up the Linux infrastructure:

## Server Setup:

1. Install Ubuntu Server:
   - Download the Ubuntu Server ISO from the official Ubuntu website.
   - Create a new virtual machine using your preferred virtualization software (e.g., VirtualBox, VMware).
   - Start the virtual machine and follow the on-screen instructions to install Ubuntu Server.

2. Install the required services:
   - DHCP server: Open a terminal and run the following command:
     ```
     sudo apt-get update
     sudo apt-get install isc-dhcp-server
     ```
   - DNS server: Run the following command:
     ```
     sudo apt-get install bind9
     ```
   - HTTP server and MariaDB: Run the following command:
     ```
     sudo apt-get install apache2 mariadb-server
     ```

3. Configure DHCP:
   - Open the DHCP configuration file for editing:
     ```
     sudo nano /etc/dhcp/dhcpd.conf
     ```
   - Define the DHCP scope for the local internal network. For example:
     ```
     subnet 192.168.1.0 netmask 255.255.255.0 {
         range 192.168.1.100 192.168.1.200;
         option routers 192.168.1.1;
         option domain-name-servers 192.168.1.10;
     }
     ```
   - Save the file and exit.

4. Configure DNS:
   - Open the DNS configuration file for editing:
     ```
     sudo nano /etc/bind/named.conf.local
     ```
   - Define the internal resources and the redirector for external resources. For example:
     ```
     zone "example.com" {
         type master;
         file "/etc/bind/db.example.com";
     };

     zone "1.168.192.in-addr.arpa" {
         type master;
         file "/etc/bind/db.192";
     };
     ```
   - Create the zone files `/etc/bind/db.example.com` and `/etc/bind/db.192` with the necessary configurations.
   - Save the files and exit.

5. Set up the internal website running GLPI:
   - Install GLPI by following the installation instructions provided by the GLPI project.
   - Configure the necessary databases in MariaDB for GLPI to function properly.

6. Weekly backup of configuration files:
   - Create a backup script by running the following command:
     ```
     sudo nano /opt/backup_script.sh
     ```
   - Add the following content to the script:
     ```bash
     #!/bin/bash

     # Backup DHCP configuration
     tar -czf /opt/dhcp_config_backup.tar.gz /etc/dhcp

     # Backup DNS configuration
     tar -czf /opt/dns_config_backup.tar.gz /etc/bind

     # Backup HTTP configuration
     tar -czf /opt/http_config_backup.tar.gz /etc/apache2

     # Backup MariaDB configuration
     tar -czf /opt/mariadb_config_backup.tar.gz /etc/mysql

     # Combine all backups into one archive
     tar -czf /opt/server_config_backup.tar.gz /opt/dhcp_config_backup.tar.gz /opt/dns_config_backup.tar.gz /opt/http_config_backup.tar.gz /opt/mariadb_config_backup.tar.gz

     # Remove individual backups
     rm /opt/dhcp_config_backup.tar.gz /opt/dns_config_backup.tar.gz /opt/http_config_backup.tar.gz /opt/mariadb_config_backup.tar.gz
     ```
   - Save the file and exit.
   - Make the script executable:
     ```
     sudo chmod +x /opt/backup_script.sh
     ```
   - Schedule the script to run weekly using `

cron`. Run the following command:
     ```
     crontab -e
     ```
   - Add the following line to the crontab file to run the backup script every Sunday at midnight:
     ```
     0 0 * * 0 /opt/backup_script.sh
     ```
   - Save the crontab file and exit.

7. Configure remote management (SSH):
   - Install OpenSSH server if not already installed:
     ```
     sudo apt-get install openssh-server
     ```
   - The SSH service should be started automatically. If not, start it using the following command:
     ```
     sudo systemctl start ssh
     ```
   - If you want the SSH service to start automatically on boot, run the following command:
     ```
     sudo systemctl enable ssh
     ```

8. (Optional) Backup on a separate disk partition:
   - Set up a separate disk and partition for backups. Refer to your specific disk partitioning tools to create the partition.
   - Mount the partition for backup:
     ```
     sudo mkdir /mnt/backups
     sudo mount /dev/sdb1 /mnt/backups
     ```
   - Update the backup script to save the backups to the mounted partition. Modify the script as follows:
     ```bash
     #!/bin/bash

     # Backup DHCP configuration
     tar -czf /mnt/backups/dhcp_config_backup.tar.gz /etc/dhcp

     # Backup DNS configuration
     tar -czf /mnt/backups/dns_config_backup.tar.gz /etc/bind

     # Backup HTTP configuration
     tar -czf /mnt/backups/http_config_backup.tar.gz /etc/apache2

     # Backup MariaDB configuration
     tar -czf /mnt/backups/mariadb_config_backup.tar.gz /etc/mysql

     # Combine all backups into one archive
     tar -czf /mnt/backups/server_config_backup.tar.gz /mnt/backups/dhcp_config_backup.tar.gz /mnt/backups/dns_config_backup.tar.gz /mnt/backups/http_config_backup.tar.gz /mnt/backups/mariadb_config_backup.tar.gz

     # Remove individual backups
     rm /mnt/backups/dhcp_config_backup.tar.gz /mnt/backups/dns_config_backup.tar.gz /mnt/backups/http_config_backup.tar.gz /mnt/backups/mariadb_config_backup.tar.gz
     ```
   - Save the file and exit.

## Workstation Setup:

1. Install Ubuntu Desktop:
   - Download the Ubuntu Desktop ISO from the official Ubuntu website.
   - Create a new virtual machine using your preferred virtualization software (e.g., VirtualBox, VMware).
   - Start the virtual machine and follow the on-screen instructions to install Ubuntu Desktop.

2. Install the required applications:
   - LibreOffice: Open a terminal and run the following command:
     ```
     sudo apt-get update
     sudo apt-get install libreoffice
     ```
   - Gimp: Run the following command:
     ```
     sudo apt-get install gimp
     ```
   - Web browser: Install a browser of your choice (e.g., Firefox, Chrome) through the software center or by downloading it from the official website.

3. Configure automatic addressing:
   - Ensure DHCP is enabled on the virtual network. The workstation will obtain the network configuration automatically.

4. Separate partition for `/home` folder:
   - Set up a separate partition during installation or using tools like `gparted`.
   - Mount the partition for the `/home` folder:
     ```
     sudo mkdir /mnt/home
     sudo mount /dev/sdb1 /mnt/home
     ```
   - Move the existing `/home` folder to the new partition:
     ```
     sudo rsync -av /home/* /mnt/home
     ```
   -

 Update the `/etc/fstab` file to automatically mount the partition on boot:
     ```
     sudo nano /etc/fstab
     ```
     Add the following line:
     ```
     /dev/sdb1 /home ext4 defaults 0 0
     ```
     Save the file and exit.

5. (Optional) Remote user assistance:
   - Install a remote desktop sharing application like `TeamViewer`, `AnyDesk`, or `VNC`. Refer to the specific documentation of the chosen application for installation instructions.
   - Configure the application to allow remote access and provide instructions to the user on how to establish a connection.

