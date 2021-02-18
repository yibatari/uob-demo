# bu-website-practical
Masters students Dev Ops practical

Use the script BETWEEN the ==== lines below in the User Data area of the EC2 instance set-up
====================================================================================== start from next line
#!/bin/bash -xe
yum install -y ruby
cd /opt
curl -O https://aws-codedeploy-eu-west-1.s3.eu-west-1.amazonaws.com/latest/install
chmod +x ./install
./install auto
sudo yum install httpd -y
sudo systemctl start httpd
====================================================================================== stop on previous line

Explanation of the above
#!/bin/bash -xe     // This line causes the bash script interpreter to process the commands, the -xe verbosely and exits on errors
yum install -y ruby // This uses yum to istall ruby, the -y indicates answer yes to all prompts. Ruby is required for codedeploy
cd /opt             // Self explanitory
curl -O https://aws-codedeploy-eu-west-1.s3.eu-west-1.amazonaws.com/latest/install  // use curl to get a copy of the codedeploy install set and save(-O) in current folder
chmod +x ./install  // Change permissions on the script previously downloaded in order to allow it to execute
./install auto      // Execute the install script 
sudo yum install httpd -y  // Similar to above, use yum to download and install httpd answering yes to all prompts
sudo systemctl start httpd // Use a system command to start the web server (httpd)
