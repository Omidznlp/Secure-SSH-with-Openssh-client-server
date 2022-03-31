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

To provide more security, disable PasswordAuthentication and change the ssh port in sshd_config \
PasswordAuthentication yes \
Port <port_number> \
![ssh-part-1](https://user-images.githubusercontent.com/87664653/159468039-fddde59f-8464-4c51-b57f-6b0e2506b07e.png)
![ssh-part-2](https://user-images.githubusercontent.com/87664653/159468311-935f5e22-3fc3-442d-9488-2660c416cdde.png)
![ssh-part-3](https://user-images.githubusercontent.com/87664653/159468062-63bd4025-4636-40c5-adbc-327c944137de.png)

## FYI

### FCS_SSHC_EXT.1 SSH Protocol - Client
FCS_SSHC_EXT.1.1 \
```
The SSH client shall ensure that the SSH protocol implementation supports the following authentication methods as described in RFC 4252: public key-based, and [selection: password-based, none].
```
FCS_SSHC_EXT.1.2 \
```
The SSH client shall ensure that, as described in RFC 4253, packets greater than [assignment: number of bytes] bytes in an SSH transport connection are dropped.
```
FCS_SSHC_EXT.1.3 \
```
The SSH software shall ensure that the SSH transport implementation uses the following encryption algorithms and rejects all other encryption algorithms: aes128-ctr, aes256-ctr, [selection: aes128-cbc, aes256-cbc, AEAD_AES_128_GCM, AEAD_AES_256_GCM, no other algorithms] .
```
FCS_SSHC_EXT.1.4 \
```
The SSH client shall ensure that the SSH transport implementation uses [selection: ssh-rsa, ecdsa-sha2-nistp256] and [selection: ecdsa-sha2-nistp384, x509v3-ecdsa-sha2-nistp256, x509v3-ecdsa-sha2-nistp384, no other public key algorithms] as its public key algorithm(s) and rejects all other public key algorithms.
```
FCS_SSHC_EXT.1.5 \
```
The SSH client shall ensure that the SSH transport implementation uses [selection: hmac-sha1, hmac-sha1-96, hmac-sha2-256, hmac-sha2-512] and [selection: AEAD_AES_128_GCM, AEAD_AES_256_GCM, no other MAC algorithms] as its data integrity MAC algorithm(s) and rejects all other MAC algorithm(s).
```
FCS_SSHC_EXT.1.6 \
```
The SSH client shall ensure that [selection: diffie-hellman-group14-sha1, ecdh-sha2-nistp256] and [selection: ecdh-sha2-nistp384, ecdh-sha2-nistp521, no other methods] are the only allowed key exchange methods used for the SSH protocol.
```
FCS_SSHC_EXT.1.7 \
```
The SSH server shall ensure that the SSH connection be rekeyed after [selection: no more than 2 28 packets have been transmitted, no more than 1 Gigabyte of data has been transmitted, no more than 1 hour] using that key.
```
FCS_SSHC_EXT.1.8 \
```
The SSH client shall ensure that the SSH client authenticates the identity of the SSH server using a local database associating each host name with its corresponding public key or [selection: a list of trusted certification authorities, no other methods] as described in RFC 4251 section 4.1.
```
### FCS_SSHS_EXT.1 SSH Protocol - Server

FCS_SSHS_EXT.1.1 \
```
The SSH server shall ensure that the SSH protocol implementation supports the following authentication methods as described in RFC 4252: public key-based, and [selection: password-based, none] .
```
FCS_SSHS_EXT.1.2 \
```
The SSH server shall ensure that, as described in RFC 4253, packets greater than [assignment: number of bytes] bytes in an SSH transport connection are dropped.
```
FCS_SSHS_EXT.1.3 \
```
The SSH server shall ensure that the SSH transport implementation uses the following encryption algorithms and rejects all other encryption algorithms: aes128-ctr, aes256-ctr, [selection: aes128-cbc, aes256-cbc, AEAD_AES_128_GCM, AEAD_AES_256_GCM, no other algorithms] .
```
FCS_SSHS_EXT.1.4 \
```
The SSH server shall ensure that the SSH transport implementation uses [selection: ssh-rsa, ecdsa-sha2-nistp256] and [selection: ecdsa-sha2-nistp384, x509v3-ecdsa-sha2-nistp256, x509v3-ecdsa-sha2-nistp256, no other public key algorithms] as its public key algorithm(s) and rejects all other public key algorithms.
```
FCS_SSHS_EXT.1.5 \
```
The SSH server shall ensure that the SSH transport implementation uses [selection: hmac-sha1, hmac-sha1-96, hmac-sha2-256, hmac-sha2-512] and [selection: AEAD_AES_128_GCM, AEAD_AES_256_GCM, no other MAC algorithms] as its MAC algorithm(s) and rejects all other MAC algorithm(s).
```
FCS_SSHS_EXT.1.6 \
```
The SSH server shall ensure that [selection: diffie-hellman-group14-sha1, ecdh-sha2-nistp256] and [selection: ecdh-sha2-nistp384, ecdh-sha2-nistp521, no other methods] are the only allowed key exchange methods used for the SSH protocol.
```
FCS_SSHS_EXT.1.7 \
```
The SSH server shall ensure that the SSH connection be rekeyed after [selection: no more than 2 28 packets have been transmitted, no more than 1 Gigabyte of data has been transmitted, no more than 1 hour] using that key.
```
## Source
Please read More information aboutExtended Package for Secure Shell (SSH) at the following link \
https://www.niap-ccevs.org/MMO/PP/-389-/
