## SSH Setup

### SSH Key Generation
```
ssh-keygen -t rsa
```
The above command will generate SSH keys. You will be left with the following files in the '.ssh' folder in the home directory of the user that ran the command:
- id_rsa - This is the private key and should be protected.
- id_rsa.pub - This is the public key that can be place in the ~/.ssh/authorized_keys files on remote systems.

### Remove Keys from known_hosts
This command is useful if the key/fingerprint for a host changes. This is often the case in lab environments as VMs are rebuilt. The command avoids needing to edit the known_hosts file manually.
```
ssh-keygen -R example.com
```
In this case example.com can be the FQDN or IP address of the target.