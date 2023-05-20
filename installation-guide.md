# Setting Up Environment for Java Development

## 1. Update the system:
sudo apt update

## 2. Install JDK and Maven:
sudo apt install default-jdk
sudo apt install maven

## 3. Install Tomcat:
mkdir apache-tomcat
cd apache-tomcat
wget https://dlcdn.apache.org/tomcat/tomcat-10/v10.1.8/bin/apache-tomcat-10.1.8.tar.gz
tar -xvzf apache-tomcat-10.1.8.tar.gz
mv apache-tomcat-10.1.8 tomcat

## 4. Configure the environment:
configure the .bashrc file and add: 

export JAVA_HOME=/usr/lib/jvm/default-java
export M2_HOME=/usr/share/maven
export CATALINA_HOME=/home/dev/Desktop/apache-tomcat/tomcat
export PATH=$PATH:$JAVA_HOME/bin:$M2_HOME/bin:$CATALINA_HOME/bin
alias start-tomcat='/home/dev/Desktop/apache-tomcat/tomcat/bin/startup.sh'
alias stop-tomcat='/home/dev/Desktop/apache-tomcat/tomcat/bin/shutdown.sh'

source .bashrc 

## 5. Install Visual Studio Code and the Extension Pack for Java.

## 6. Create a Maven project and build it:
mvn clean install

## 7. Deploy the Maven project to Tomcat:
sudo cp target/webapp.war /home/dev/Desktop/apache-tomcat/tomcat/webapps/
sudo chmod 644 webapp.war

## 8. Start Tomcat:
start-tomcat
