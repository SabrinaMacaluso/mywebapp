# mywebapp

##  Update the system packages:

```sudo apt update```

* Install the default JDK (Java Development Kit):

```sudo apt install default-jdk```

* Install Maven (a build automation tool for Java projects):

```sudo apt install maven```

* Download Apache Tomcat (version 10):

* Create a directory for Apache Tomcat:

```mkdir apache-tomcat```

```cd apache-tomcat```

* Download Apache Tomcat 10.1.8:

```wget https://dlcdn.apache.org/tomcat/tomcat-10/v10.1.8/bin/apache-tomcat-10.1.8.tar.gz```

* Extract the downloaded archive:

```tar -xvzf apache-tomcat-10.1.8.tar.gz```

* Rename the extracted folder to "tomcat":

```mv apache-tomcat-10.1.8 tomcat```

* Create a directory for web applications:

```mkdir tomcat/webapps```


## Configuration in Visual Studio Code:

* Install the Extension Pack for Java by Microsoft.

* Create a Maven project using the "webapp" archetype. Choose a name for your project (e.g., "webapp").

* In the Visual Studio Code terminal, run the following command to clean and build the Maven project:

```mvn clean install```

* Copy the generated WAR file to the Tomcat webapps directory:

```sudo cp target/webapp.war /home/dev/Desktop/apache-tomcat/tomcat/webapps/```

* Start Tomcat using the following alias:

```start-tomcat```

## Accessing your web application:

* To access your web application, open a web browser and go to the following URL:

```http://localhost:8080/webapp/```

## Environment configuration:

Open the .bashrc file.

* Add the following environment variables:

```export JAVA_HOME=/usr/lib/jvm/default-java```

```export M2_HOME=/usr/share/maven```

```export CATALINA_HOME=/home/dev/Desktop/apache-tomcat/tomcat```

```export PATH=$PATH:$JAVA_HOME/bin:$M2_HOME/bin:$CATALINA_HOME/bin```

* Define aliases for starting and stopping Tomcat:

```alias start-tomcat='/home/dev/Desktop/apache-tomcat/tomcat/bin/startup.sh'```

```alias stop-tomcat='/home/dev/Desktop/apache-tomcat/tomcat/bin/shutdown.sh'```

* Apply the changes by sourcing the .bashrc file:

```source ~/.bashrc```


# troubleshooting

To troubleshoot any issues, add the following code to the server.xml file in the tomcat/conf directory:

|```<Host>```
 ``` <Context path="/webapp" docBase="webapp" />```
```</Host>```

Replace "webapp" with the correct path, save the file and restart tomcat: 

```start-tomcat```



