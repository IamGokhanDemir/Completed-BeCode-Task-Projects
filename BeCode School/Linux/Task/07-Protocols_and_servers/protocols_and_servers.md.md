
# Protocols and Servers

## Goals

1. **HTTP/HTTPS**
   - Configure a virtual host
   - Deploy a one-pager
2. **SSH**
   - Configure key-based authentication
3. **SMB**
   - Provide network shares to specific clients
4. **TELNET**
   - Install and configure
5. **FTP**
   - Install and configure

## HTTP, FTP, SMTP, POP3, IMAP, SMB

First, please follow this PDF guide: [http://dma.vgtu.lt/KTA/KTA10_EN.pdf](http://dma.vgtu.lt/KTA/KTA10_EN.pdf)

## Exercises

> Connect to the virtual machine `10.12.181.X` with the following credentials:
> - IP: `10.12.181.X`
> - User: `student`
> - Password: `student`

1. On your Kali (or other) machine, install `nginx` to have an HTTP server on port 8080. Replace the default page of nginx with an HTML page displaying "Hello, world!".

   > No answer required

2. What other well-known service could be used instead of nginx?

   > Your answer: `ApacheHTTPServer known as Apache`

3. On your student machine, create a temporary HTTP server with Python on port `5000`. Then, on your Kali machine, open a browser and go to the address `10.12.181.X:5000`.

   > Your command: `python3 -m http.server 5000
`

4. Let's imagine that a hacker owns the domain name `g00gle.com`. Which tool would allow them to obtain an SSL certificate (HTTPS) very easily?

   > Your answer: `Let's Encrypt`

5. On a Linux machine, what tool could you use to have a self-signed SSL certificate on your local machine (localhost)?

   > Your answer: `OpenSSL`
   > example command: 
   > `openssl req -x509 -nodes -days 365 -newkey rsa:2048 -keyout localhost.key -out localhost.crt`

6. On your student machine, install the FTP service and connect from your Kali machine.

   > No answer required

7. What is the default port for FTP?

   > Your answer:`The default port for FTP is 21`

8. Is the FTP protocol secured?

   > Your answer: `No, FTP (File Transfer Protocol) is not secure by default. FTP transmits data, including usernames, passwords, and files, in plain text. This means that any data sent over an FTP connection can be intercepted and read by anyone with access to the network.`

9. On your student machine, install the Telnet service and connect from your Kali machine.

   > No answer required

10. What is the default port for Telnet?

    > Your answer: `The default port for Telnet is 23

11. Is the Telnet protocol secured?

    > Your answer: `No, the Telnet protocol is not secure. Telnet transmits data, including usernames, passwords, and commands, in plain text. This means that any data sent over a Telnet connection can be intercepted and read by anyone with access to the network.`

12. Create a shared file with Samba between your Kali machine and your student machine.

    > No answer required