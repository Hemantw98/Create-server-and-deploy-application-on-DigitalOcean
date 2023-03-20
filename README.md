## Project: Create server and deploy application on DigitalOcean.
**Setup and configure a server on DigitalOcean.**

1. Create a DigitalOcean account: Go to the DigitalOcean website (https://www.digitalocean.com/) and create an account. You will need to provide your name, email address, and a password.

2. Create a droplet: Once you have created an account, you can create a droplet by clicking on the "Create" button and selecting "Droplets" from the dropdown menu.

3. Choose a droplet image: Select a droplet image based on your needs. For example, if you want to set up a web server, you can choose a LAMP or a Nginx image. You can also choose the size of your droplet and the location of the server.

4. Add SSH keys: Add an SSH key to your droplet so that you can access it securely. If you don't have an SSH key, you can generate one using the ssh-keygen command.

5. Log in to your server: Once your droplet is created, you can log in to your server using SSH. To do this, open a terminal and type the following command: ssh root@your_server_ip_address

6. Install software: Once you are logged in, you can install any software you need on your server. For example, if you want to deploy a Node.js application, you can install Node.js and NPM.

7. Upload your application: You can now upload your application to your server using FTP or SCP(Secure copy). For example, if you have a Node.js application, you can upload the files to the /var/www directory.

8. Install dependencies: Once your application is uploaded, you can install any dependencies by running the following command: npm install

9. Start your application: Finally, you can start your application by running the following command: npm start

10. Configure your firewall: Make sure to configure your firewall to allow traffic to your application. For example, if you are using Nginx, you can configure your firewall to allow traffic on port 80.


### Create and configure a new Linux user on the Droplet (Security best practice).
***

Creating a new Linux user on your DigitalOcean droplet is a security best practice. Here are the steps to follow:


1. Log in to your droplet: Log in to your droplet as the root user using SSH.
`ssh root@ip_address`

2. Create a new user: To create a new user, run the following command:
`adduser username`

Replace "username" with the desired username for the new user.

3. Set a password: Set a password for the new user by running the following command:
`passwd username`

Replace "username" with the username you created in step 2.

4. Grant sudo privileges: If you want the new user to have sudo privileges, you can add the user to the sudo group by running the following command:
`usermod -aG sudo username`

Replace "username" with the username you created in step 2.

5. Configure SSH access: To allow the new user to access the droplet via SSH, you need to copy the root user's SSH key to the new user's home directory. To do this, run the following command as the root user:
bash

`rsync --archive --chown=username:username ~/.ssh /home/username`
Replace "username" with the username you created in step 2.

6. Test the new user: Log out of your droplet and log back in as the new user using SSH. Test that you can run commands and access files on the droplet.

That's it! You have now created and configured a new Linux user on your DigitalOcean droplet following security best practices.


### Deploy and run a Java Gradle application on Droplet.
***

+ In order to run Java grade application on remote Server, we will first build the jar file locally and then from there we will copy the jar file to our remote server.

+ For that we will take an example of [java react project](https://github.com/nanuchi/java-react-example).

+ Clone the java react project locally. Upon cloning, inside the project root folder we are going to execute the gradle build command which is given below:-

  `./gradlew build`

+ Execute below command to copy .jar file from locally to the remote server.

  `scp build/libs/java-react-example.jar root@ipaddress:/root`

+ Once you execute the above command, login to remote sever and we will be able to see the .jar file present in the /root directory.

+ In order to run the aplication, execute to below command:-

  `java -jar java-react-example.jar`

+ Voila! Our application has now started.

Technologies used:-DigitalOcean, Linux, Java, Gradle.

Related Project

+ [Java-react-example
](https://github.com/nanuchi/java-react-example)
