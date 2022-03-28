# Secure-SSH-with-Openssh-client-server
If you use openssh in a production environment, Follow the instructions to provide a secure SSH based on the Extended Package for Secure Shell (SSH) NIAP. Furthermore, it provides more options for increasing security.
## Configuration
Client configuration file \
    • /etc/ssh/ssh_config \
Server configuration file \
    • /etc/ssh/sshd_config \
Apply configuration \
    • sudo systemctl restart ssh \
Guideline for ssh client configuration \
    • https://man7.org/linux/man-pages/man5/ssh_config.5.html \
Guideline for ssh server configuration \
    • https://man7.org/linux/man-pages/man5/sshd_config.5.html \
Version of openssh \
    • OpenSSH_7.6p1 
  
Note: The parameters listed in the table should be added to the SSH server and client configuration files that have already been prepared and uploaded to this repository, and should be replaced in their respective paths.

To provide more security, disable PasswordAuthentication in sshd_config and change the ssh port\
PasswordAuthentication yes \
Port <port_number> 
![ssh-part-1](https://user-images.githubusercontent.com/87664653/159468039-fddde59f-8464-4c51-b57f-6b0e2506b07e.png)
![ssh-part-2](https://user-images.githubusercontent.com/87664653/159468311-935f5e22-3fc3-442d-9488-2660c416cdde.png)
![ssh-part-3](https://user-images.githubusercontent.com/87664653/159468062-63bd4025-4636-40c5-adbc-327c944137de.png)

## FYI
Please check Extended Package for Secure Shell (SSH) \
https://www.niap-ccevs.org/MMO/PP/-389-/ \
FCS_SSHC_EXT.1.4 \
FCS_SSHS_EXT.1.4 \
FCS_SSHC_EXT.1.5 \
FCS_SSHS_EXT.1.5 \
FCS_SSHC_EXT.1.6 \
FCS_SSHS_EXT.1.6 \
FCS_SSHC_EXT.1.7 \
FCS_SSHS_EXT.1.7 \
FCS_SSHC_EXT.1.8 \
FCS_SSHS_EXT.1.8 \
