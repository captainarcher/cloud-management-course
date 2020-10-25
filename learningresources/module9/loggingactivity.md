# Logging Activity
## Follow the instructions for your chosen Linux distribution
<br>

## Instructions for Ubuntu/Debian Linux
1. Install Java on your Linux machine.  OpenJDK 14 or 15 are required.  Use this command to install Open JDK 14.
```
sudo apt install openjdk-14-jre-headless
```
2. Download Elasticsearch
```
curl -L -O https://artifacts.elastic.co/downloads/elasticsearch/elasticsearch-7.9.3-amd64.deb
```
Note: if you do not have curl installed, use ```sudo apt install curl```.<br>
3. Install Elasticsearch
```
sudo dpkg -i elasticsearch-7.9.3-amd64.deb
```
4. Start elasticsearch
```
sudo /etc/init.d/elasticsearch start
```

## Instructions for RedHat/Amazon Linux/Fedora/CentOS

1. Download Java to your Linux machine.  OpenJDK 14 or 15 are required.  
***Note: If you do not have wget installed, use ```sudo yum install wget```***<br>
```
wget https://download.java.net/java/GA/jdk14.0.2/205943a0976c4ed48cb16f1043c5c647/12/GPL/openjdk-14.0.2_linux-x64_bin.tar.gz
```
2. Move the Java installer to /usr/local/bin
```
sudo mv openjdk-14*_bin.tar.gz /usr/local/bin/
```
3. Switch to the /usr/local/bin directory
```
cd /usr/local/bin
```
4. Extract the Java installer.
```
tar -xvf openjdk-14*_bin.tar.gz
```
5. Go inside the JDK bin directory.
```
cd openjdk-14.0.2/bin/
```
6. Run the Java command
```
./java -version
```
7. Ensure that /usr/local/bin is in your PATH
```
echo $PATH
```
If you see something similar to this, then move to the next step - you can skip over the rest of this step: ```/usr/local/sbin:/usr/local/bin:/usr/sbin:/usr/bin:/sbin:/bin```

If you do not see /usr/local/bin, then open your user profile (~/.bashrc) and add the following:
```
export PATH=/usr/local/bin:$PATH
```
If you don't have this file in your home directory, then create it.<br>
After the profile has been saved, reload your profile.
```
source .bashrc
```
<br>
Verify that the path has /usr/local/bin in it using ```echo $PATH```
<br>
Verify that the correct java is being used:<br>
```
which java
```
You should see version 14.

8. Download Elasticsearch
```
curl -L -O https://artifacts.elastic.co/downloads/elasticsearch/elasticsearch-7.9.3-x86_64.rpm
```
Note: if you do not have curl installed, use ```sudo yum install curl```.<br>
3. Install Elasticsearch
```
sudo rpm -i elasticsearch-7.9.3-x86_64.rpm
```
4. Start elasticsearch
```
sudo service elasticsearch start
```
