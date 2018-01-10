# gibson

Pentest walkthrough for VulnHub.com Gibson VM. This is a theme VM based on the movie 'Hackers'.


## netdiscover

Use netdiscover to identify the IP address of the Gibson VM

![Alt text](./netdiscover.png?raw=true)


## nmap

Nmap was used to identify open service ports on the VM

![Alt text](./nmap.png?raw=true)


## browser

Browsing to the home page gives us a link to a page with sensitive information in the HTML source.

![Alt text](./browser-source.png?raw=true)


## ssh

Usng the compromised information from the HTML comment, we can SSH to the VM as margo and 'god' as the password.

![Alt text](./low-priv-shell.png?raw=true)


## /etc/passwd

A 'cat' on /etc/passwd file shows additional users. 

![Alt text](./etc-passwd.png?raw=true)


Using the 'eugene' user and brute forcing with 'Hackers' passwords, we get a shell with 'secret'.

![Alt text](./script.png?raw=true)

![Alt text](./eugene-shell.png?raw=true)


## sudo command

Running 'sudo -l' lists the sudo commands for the 'eugene' user. 'visudo' command is the path to elevated privileges.

![Alt text](./sudo-dash-el.png?raw=true)

![Alt text](./visudo1.png?raw=true)

![Alt text](./visudo2.png?raw=true)



## root

<pre>
\(*_*)
  ( (>
  /  \
</pre>

Once the '/etc/sudoers' file has been updated, exit out of the 'eugene' shell, then 'su' back in and 'sudo' to root.

![Alt text](./root.png?raw=true)
