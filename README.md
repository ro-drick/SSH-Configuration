# Packet Tracer - Configuring SSH
<br/>
<p align="center">
  <img src="https://github.com/ro-drick/SSH-Configuration/blob/main/SSH.png"/>
</p>
<br/>


## Addressing Table

| Device | Interface | IP Address  | Subnet Mask    |
|--------|-----------|-------------|----------------|
| S1     | VLAN 1    | 10.10.10.2  | 255.255.255.0  |
| PC1    | NIC       | 10.10.10.10 | 255.255.255.0  |

## Objectives

1. **Secure Passwords**
2. **Encrypt Communications**
3. **Verify SSH Implementation**

## Background

SSH should replace Telnet for management connections. Telnet uses insecure plain text communications, while SSH provides security for remote connections by encrypting all transmitted data between devices. In this activity, you will secure a remote switch with password encryption and SSH.

---

## Part 1: Secure Passwords

1. Using the command prompt on PC1, Telnet to S1. The user EXEC and privileged EXEC password is `cisco`.
2. Save the current configuration so that any mistakes can be reversed by toggling the power for S1.
3. Show the current configuration and note that the passwords are in plain text. Enter the command to encrypt plain text passwords.
4. Verify that the passwords are encrypted.

---

## Part 2: Encrypt Communications

### Step 1: Set the IP domain name and generate secure keys.

Telnet is unsafe as data is transferred in plain text. Therefore, use SSH whenever it is available.

1. Configure the domain name to be `netacad.pka`.
2. Generate the RSA keys using a 1024 key length to encrypt the data.

### Step 2: Create an SSH user and reconfigure the VTY lines for SSH-only access.

1. Create an administrator user with `cisco` as the secret password.
2. Configure the VTY lines to check the local username database for login credentials and allow only SSH for remote access. Remove the existing VTY line password.

---

## Part 3: Verify SSH Implementation

1. Exit the Telnet session and attempt to log back in using Telnet. The attempt should fail.
2. Attempt to log in using SSH. Type `ssh` and press Enter without any parameters to reveal the command usage instructions.  
   *Hint: The `-l` option is the letter “L”, not the number 1.*
3. Upon successful login, enter privileged EXEC mode and save the configuration. If you were unable to successfully access S1, toggle the power and begin again at Part 1.
