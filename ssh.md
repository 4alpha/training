1. What is Secure Shell(SHH) ?
2. What are the uses of SHH ?
3. How to connect remote machine using SHH?
4. Generating a key
5. Public key, Private key 
6. How to copy file from local machine to remote machine ?
7. How to change the permission of file ?
8. How to end your SSH session ?

*setting environment for ssh* <br>
1. commands for installing ssh <br>
  sudo service ssh status <br>
  sudo apt-cache search openssh
  sudo apt-get install openssh-server
2. commands for connection establishment
  *with password*
    cd /home/.ssh/
    ssh developer@"ip adress of server machine"
  *without password*
    ssh-keygen -t -rsa    //generating keys (privet and public)
    scp id_rsa.pub developer@"server's ip"
    ssh developer@"ip adress of server machine"
    //At server side machine
      cd .ssh
      cat id_rsa.pub >> /home/.ssh/authorized_keys
      chmod 644 authorized_keys
      cd ..
      chmod 755 .ssh
      
  
