# RuneLight

RSPS website project.



# Local (Development) Setup

Download and setup Tomcat + MySQL Server:

Set Tomcat to port 80 (if desired) and MySQL to 3306.


runelight.properties:
Copy file into Tomcat/conf/


In Tomcat/conf/server.xml:
Under <Host name="localhost" appBase="webapps"
            unpackWARs="true" autoDeploy="true">

add

<Context path="" docBase="runelight-RUNELIGHTVERSIONHERE" debug="0" reloadable="true" />

ie

<Context path="" docBase="runelight-0.0.1" debug="0" reloadable="true" />


In Tomcat/conf/context.xml add a new jdbc resource:

<Resource name="jdbc/runelight" auth="Container"
		  type="javax.sql.DataSource" 
		  username="root" password="mysql"
		  driverClassName="com.mysql.jdbc.Driver"
		  url="jdbc:mysql://127.0.0.1:3306/runelight" 
		  maxActive="15" maxIdle="3" />


Add some subdomains/domains to your Windows hosts file (in whichever format you wish, the following is what I use):
127.0.0.1             runelight.giselle
127.0.0.1             www.runelight.giselle
127.0.0.1             create.runelight.giselle
127.0.0.1             news.runelight.giselle
127.0.0.1             forum.runelight.giselle

etc, etc...
		  

Add two environment variables:
JAVA_HOME=the/path/to/your/java/installation/ (should have been done in order to run Tomcat)
RS_HOMe=the/path/to/your/RuneLight/repo/

Restart all CMD windows.


Run RuneLight/scripts/deploy.sh


...


Profit???
