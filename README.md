# Infotrixis
Task1:
For monolith: 1 EC2 instance create, deploy WordPress and MYSQL on the same instance. create a simple webpage

Pre-requisites: • Configure the necessary security group for the instances. • EC2 instance type: t2 micro, AMI: Ubuntu

Step 1: Login to AWS free tier account. Search for EC2 instance in the dashboard.
Step 2: Create one EC2 instance on AWS.
• Name: monolithec2-task1 • AMI: Ubuntu. • Instance Type: t2.micro • Key pair: monolith-key (new created)

Step 3: Allowed inbound traffic for SSH, HTTP/HTTPS (port 80 and 443) for WordPress access and port 3306 for MySQL access.
Step 4: The EC2 Instance launched Successfully->Click on connect to further process.
Step 5: To connect the Ubuntu, we need to copy the ssh.
Step 6: Open terminal, go to the download folder (where our security key is downloaded)
cd downloads

paste the ssh path (copied above) on terminal to connect our Ubuntu server with our EC2 instance.
Step 7: Installed apache2 server on Ubuntu.
sudo apt install apache2

Step 8: Now copy the public IP of the EC2 and paste on the new tab
http://<public-ip>

The Apache2 Default page open means our wordpress is up and running successfully.
Step 9: Installed php runtime and php mysql connector.
sudo apt install php libapache2-mod-php php-mysql

Step 10: Intalled MySql Server.

sudo apt install mysql-server

Step 11: Login to MySql Server

sudo mysql -u root

Step 12: Change authentication plugin to mysql_native_password (Choose strong Password)
ALTER USER 'root'@localhost IDENTIFIED WITH mysql_native_password BY 'Tejas@123';

Step 13: Create new database user for wordpress
CREATE USER 'Tejas'@localhost IDENTIFIED BY 'Tejas@123';

Step 14: Create a database for wordpress
create database wordpress;

Step 15: Grant all Privileges on the database ‘wordpress’ to the newly created user.
GRANT ALL ON *.* TO 'Tejas'@localhost;

Step 16: For download wordpress ->go to the wordpress.org website on Google, copy the download link.
`https://wordpress.org/latest.tar.gz'

Step 17: on terminal type command as:
cd /tmp wget https://wordpress.org/latest.tar.gz ls

Step 18: Extract the zip file.
tar -xvf latest.tar.gz

Step 19: Now WordPress is successfully installed.
ls

Step 20: wordpress file contain index.html
index.html wordpress
Step 21: Unzip the file
tar -xvf latest.tar.gz

Step 22: Move Wordpress folder to apache document root
sudo mv wordpress/ /var/www/html

Step 23: Command to restart apache server
sudo systemctl restart apache2 OR sudo systemctl reload apache2

Step 24: Now copy the public IP of the EC2 and paste on the new tab as below,
http://<public-ip-of-ec2>/wordpress

Step 25: go to next step and fill all details – database name, username & password.
1. Database Name : wordpress
2. Username : Tejas
3. Password : 'YourPassword'
4. Database Host : localhost
5. Table Prefix : wp_
>Click on submit button
Step 26: wp-config.php error occur to fix it copy the code given in wp-config.php.
>
Step 27: on the terminal, inside wordpress folder-> create nano wp-config.php file and paste above copied code.
cd wordpress nano wp-config.php

Step 28: Click on Run the installation button.
Go back to the browser and RUN the INSTALLTION 👍

Step 29: Fill all the details to host/deploy your webpage.
Here the error is resolved!
Need to configure the information

Step 30: Now install wordpress and Login with username & password.
Click on Install WordPress:
WordPress is installed successfully -
login the WordPress with username and password that you have already created!

Step 31: See your first webpage is open successfully on the wordpress.
Welcome to My WordPress Website

STEP 32: Log into WordPress Admin.
Access your WordPress dashboard by going to your website's URL followed by "/wp-admin" (e.g., IPV4/wp-admin). Log in using your credentials.

STEP 33: Create a New Page.
In the WordPress dashboard, go to "Pages" and click on "Add New" to create a new page.
Add a Title: Enter a title for your welcome page. For example, you can use "Infotrixis"

STEP 34: Publish the Page.
Click the "Publish" button on the right side of the page editor to make your welcome page live. If you're not ready to publish it immediately, you can click "Save Draft" to come back to it later.

STEP 35: Set as Homepage.
If you want your welcome page to be your website's homepage, you can set it as such. To do this, go to "Settings" > "Reading" and choose "A static page" under "Front page displays." Select the welcome page you created from the drop-down menu.

Conclusion: successfully performed my 1st task for monolith. In that 1 EC2 instance created, deployed WordPress and MYSQL on the same instance and created welcome page as “Welcome to My WordPress Website” as homepage.


