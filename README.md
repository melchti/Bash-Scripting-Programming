# Bash-Scripting-Programming
This assignment evokes the role of a hacker. I remotely access a victim's target machine, maintain access using a backdoor, and crack sensitive passwords in the /etc directory.

In the final unit of our introduction to Linux system administration, I learned how to combine commands, create custom commands, and write bash scripts.

•	I used these skills to collect logs, audit and reconfigure a Linux machine, and take steps to harden the system.

•	In Day 3, I participated in a Linux Scavenger Hunt. This extended activity put to use all the skills and tools covered in the past three units.


The Scenario for this assignment was as follows:

In this week's homework you will play the role of a hacker. You will remotely access a victim's target machine, maintain access using a backdoor, and crack sensitive passwords in the /etc directory.

You will be learning a lot of new concepts in this homework, and you may need to do a bit of research. This homework should be a fun, engaging hands-on introduction to maintaining access to a compromised system. You will learn about this in more depth during the pentesting units. For now, read the section below on Privilege Escalation to better understand the setup and goal of this assignment.

•	Note: This activity is based on the "offense informs defense" philosophy. You will practice taking the role of a criminal hacker in order to better understand how exploits are carried out. Remember: to protect from attacks, you'll need to practice thinking like an attacker.

Privilege Escalation

When an attacker gains access to a machine, their first objective is always to escalate privileges to root (which you accomplished during your scavenger hunt activity). When they achieve root privileges, they can do anything they want to the system. Cybersecurity professionals describe the process of gaining access to a host and escalating to root privileges as owning the system.

While owning a system is a crucial piece of the process, it is only the first item on an experienced attacker's agenda. Two goals remain on the checklist: maintaining access and exfiltrating data.

After exploiting a machine, attackers must ensure they will be able to reconnect later with the same escalated privileges they gained during the first assault. This is typically achieved by installing a backdoor. A backdoor is any mechanism that allows an attacker to secretly reconnect to a machine they've exploited.



Steps used to complete task:

1. I created a “sysd” user with a password, system UID, GID and granted sudo access without a password.
2. I tested that the sysd user can execute commands with sudo access without a password before moving on.
3. I use Nano to update the /etc/ssh/sshd_config configuration file to allow SSH access via port 2222.
4. I restarted the SSH service.
5. I exited the root account, and logged off of the target machine.
6. I used my attacking machine to test the new backdoor SSH port with ssh sysd@192.168.6.105 -p 2222.
7. I used sudo su to switch back to the root user.
8. I used “John the ripper” to crack the entire /etc/shadow file.


