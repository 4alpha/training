1. What is Secure Shell(SHH) ?
2. What are the uses of SHH ?
3. How to connect remote machine using SHH?
4. Generating a key
5. Public key, Private key 
6. How to copy file from local machine to remote machine ?
7. How to change the permission of file ?
8. How to end your SSH session ?

**setting environment for ssh** <br>
* 1. commands for installing ssh <br>
  * sudo service ssh status <br>
  * sudo apt-cache search openssh <br>
  * sudo apt-get install openssh-server <br>
* 2. commands for connection establishment <br>
  * **with password** <br>
    * cd /home/.ssh/ <br>
    * ssh developer@"ip adress of server machine" <br>
  * **without password** <br>
    * ssh-keygen -t -rsa    //generating keys (privet and public) <br>
    * scp id_rsa.pub developer@"server's ip" <br>
    * ssh developer@"ip adress of server machine" <br>
    * //At server side machine <br>
      * cd .ssh <br>
      * cat id_rsa.pub >> /home/.ssh/authorized_keys <br>
      * chmod 644 authorized_keys <br>
      * cd .. <br>
      * chmod 755 .ssh <br>
      
  
