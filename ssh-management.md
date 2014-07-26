# SSH Keys

Utilizing SSH keys in conjunction with the servers you connect to is a great and highly recommended security practice. SSH keys help the server validate and authenticate who you are. SSH servers can even be setup to require a known valid SSH key in order for the server to acknowledge you to begin the login process.

Using SSH from a Linux or Mac system is straightforward and easy. You may not realize it but your system will automagically generate an SSH key for you the first time you use SSH if you do not have one already. This key will then be sent with all subsequent request to that server and all other servers. This is a great start, however it is possible to maintain multiple SSH keys on your system. 

If the one SSH key allows you to get into all your systems why would you want additional keys? Simple, extra security. Having a unique key per system you are logging into will create additional security by only allowing that key to be used on that system and no other. If your account somehow gets compromised and the key to the server taken you do not have to worry about all the systems you have logged into with that key and remember to go secure them. You simply delete the key for that system and generate another.

Managing multiple keys is easy. Let me show you how you can accomplish this on your own system.

## Where to find SSH files
All the SSH files live in a hidden folder ```.ssh``` in your user directory. If your system is using the generic key file this folder may not exist. You can safely create this folder yourself. We will be working out of it for the remainder of this tutorial.

We will also be working from the terminal for the rest of this process. 

Open up your terminal and get setup.

```cd ~/.ssh```

If you get an error that the directory does not exist create it with:

```mkdir ~/.ssh```

## Lets make some keys!
For this example we will setup keys for two servers: abc.com and xyz.com.

SSH includes a simple utility for creating SSH keys called ```ssh-keygen``.  The following is an example of what creating a key would look like.

```
blobaugh@devbox$ ssh-keygen
Generating public/private rya key pair.
Enter file in which to save the key (/Users/blobaugh/.ssh/id_rsa): [id_rsa.abc.com]
Enter passphrase (empty for no passphrase): [Enter a passphrase]
Enter same passphrase again: [Repeat passphrase]
Your identification has been saved in /Users/blobaugh/.ssh/id_rsa.abc.com
Your public key has been saved in /Users/blobaugh/.ssh/id_rsa.abc.com.pub
The key fingerprint is:
[Long crazy string]
The key’s random art image is:
[Cool ascii art]
```

Type ```ls``` into the terminal and you should now see two new key files that have been created for abc.com. Repeat the process with xyz.com.

Passphrases are recommended but not strictly necessary. If you are creating a passwordless login you can hit enter to leave it blank. Later on when we get into the configuration file there are additional login options you can set.

Since you are now a pro at creating SSH keys I suggest you also create a generic key. This key will be used on any systems you login to where you do not have a unique key created. 

## Setup the configuration file
Likely there will not be a configuration file in your ```.ssh``` directory. This is normal. You will create it in this step. 

To utilize your shiny new SSH key with a specific system you will need to create a new entry into the ```~/.ssh/config``` file related to that host. You can use either the hostname or the IP. One key can have multiple entries, so if you have multiple hostnames for one system, or want to use both the hostname and IP to login simply create an additional entry in the config file. The * wildcard can also be used.

To get started open the ```~/.ssh/config``` file in your editor of choice and add the following lines:

```
Host abc.com
    IdentityFile ~/.ssh/id_rsa.abc.com

Host xyz.com
    IdentityFile ~/.ssh/id_rsa.xyz.com
```

That is it! You will now be utilizing a different key for each of those hosts.

Setup the generic key with

```
Host *
    IdentityFile ~/.ssh/id_rsa.generic
```

## Configuration options
There are many configuration options available to you in this file. Lets break down a few here.

**Host**
The Host option is a bit tricky. Host is for the name you use on the command line with the ssh command. This does not have to be a real machine but can be an alias. When used as an alias you need to supply the HostName option as well. Here are a couple example to help make this more clear.
 ```
Host lobaugh.net
    ….
````
On the command line you would use ```ssh yahoo.com``` to connect to the machine still.

```
Host ben
    HostName lobaugh.net
    ….
```
In this example you would call ```ssh ben```  and still be connected to the lobaugh.net server.


**User**
Allows you to set the username that is supplied to the connection by default. This can be different than the currently logged in user that is supplied by the system if one is not supplied. This setting can be overwritten at run time on the command line.

```
Host lobaugh.net
    User ben
```

**ServerAliveInterval**
Some servers have a timeout setting that will automatically disconnect a user if they do not perform an action for a specified period of time. This is great for security, however some hosts are a bit aggressive with disconnects and will bump you rather quickly (looking at you MediaTemple). This option tells your client to send keep alive packets to the server so you do not get disconnected too quickly. This setting is in seconds.

```
Host lobaugh.net
    ServerAliveInterval 60
```

**IdentityFile**
This is the key file we created in the beginning that should be used for the connection.

```
Host lobaugh.net
    IdentityFile ~/.ssh/id_rsa.lobaugh.net
```

**Port**

Allows changing the port number the connection uses for non-standard ports.

```
Host lobaugh.net
    Port 5000
```

A complete list of configuration options can be found at http://www.gsp.com/cgi-bin/man.cgi?topic=ssh_config

## Setup the server side of things
Now that we have things on the client side setup we need to let the server know what is happening. This will ensure that the server knows who we are. This is as simple as ensuring the public key is present in the authorized_keys file.

We will use a couple “magic” ssh commands that run remote commands on the server for us.

First we need to ensure the .ssh directory exists on the server or the transfer of the key will fail.

```
ssh USER@SERVER mkdir ~/.ssh
```

Now we will send the **public** key to the server.
```
cat .ssh/KEY_FILE.pub | ssh USER@SERVER ‘cat >> .ssh/authorized_keys’
```

You are now all set with multiple unique keys per machine you are connecting into, complete with verification of the key on the server side of things.
