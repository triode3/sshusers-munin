# README 
for the sshusers plugin for adding the total number of ssh connections and users to [Munin](https://munin-monitoring.org/)

This readme is broken into a few small sections: What,  Why, How to install, How to change, License. 

# What is this thing?

This readme assumes you know what [Munin](https://munin-monitoring.org/) is all about, and that you want to graph the number of ssh connections to some box that munin is monitoring. 

# Why did I make this?

We have some servers which are the login nodes of our cluster, and fairly often the question of "well, how many users are on login node n?" comes up. Then one or more of us goes to login node n
and starts looking around. Of course, this is usually after the fact/event/whatever, and so it dawned on me that perhaps we could just graph it in munin. 

# How to install it.

It is a plugin just like any munin plugin, so you need to do the following:

- place the sshusers file into /usr/share/munin/plugins (or if you moved it, the munin plugin dir)
- create a link from /etc/munin/plugins/sshusers to /usr/share/munin/plugins/sshusers
- restart munin-node
- restart munin (if you want to). 

Again, if you moved munins plugins dir, change the links to relect this. 

# How to change it, etc. 

**NOTE** There are multiple ways to check for the number of ssh users on a linux box. Due to that, you can choose which method you think is best for you by editing the sshusers file. In that file, there are multiple commands to check for ssh users, with comments on each one above its respective method. 

**NOTE** the resulting output will be two numbers on each graph, the total number of users (e.g. includes repeats) and a "pretty good" guess of the number of active users that are not repeated. 


# LICENSE

GNU GENERAL PUBLIC LICENSE (see LICENSE.md)

A copy of the GPL3 is included with this software. (see gpl-3.0.txt)




