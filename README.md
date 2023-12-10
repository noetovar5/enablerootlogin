# enablerootlogin
enable root login over ssh
Enable root login over SSH

1.Login to your server as root.

2.As the root user, edit the sshd_config file found in /etc/ssh/sshd_config:
vim /etc/ssh/sshd_config
(For details on working with Vim check out our article here!)

3.Add the following line to the file, you can add it anywhere but it’s good practice to find the block about authentication and add it there.
PermitRootLogin yes

4.Save and exit the file.

5.Restart the SSH server:
systemctl restart sshd

or
service sshd restart


And that’s it! With the new line added and the SSH server restarted, you can now connect via the root user.

In this instance, you are going to be able to login as the root user utilizing either the password or an ssh key.

When using SSH Keys, you can set the PermitRootLogin value to `without-password` instead of yes. To accomplish this, simply modify the following information noted in step 2 above instead:

PermitRootLogin without-password
