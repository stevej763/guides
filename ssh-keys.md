## Creating ssh keys and copying them to a remote machine for passwordless login (or with a passphrase if needed)

1. Generate a new ssh key on your local machine if needed
   - you will be given the option to rename the default file name if needed
   - you can then chose to enter a password, or leave it blank for passwordless login

```
ssh-keygen -t rsa -b 4096 -C "my ssh key"
```

2. Use the `ssh-copy-id` command to ssh onto the remote server and copy the key into the authorised-keys file.
   - you will need to enter the password of the remote user on the machine you are trying to copy the key over to

```
ssh-copy-id remote_machine_user@remote_machine_ip_or_hostname
```

3. Test logging in with the key
   - if you did not provide a password when generating the keys, you should be logged in without any need to enter a password

```
ssh remote_machine_user@remote_machine_ip_or_hostname
```
