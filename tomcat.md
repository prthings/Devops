## Tomcat Installation
Copy this below code and paste in server and install tomcat

``` wget https://dlcdn.apache.org/tomcat/tomcat-9/v9.0.80/bin/apache-tomcat-9.0.80.tar.gz ```

Now Extract using tar

``` tar -zxvf apache-tomcat-9.0.80.tar.gz ```

Rename the apache-tomcat-9.0.80 directory

``` mv apache-tomcat-9.0.80 apache9 ```

now goto apache > conf > add users to tomcat by accesing tomcat

``` <role rolename="manager-gui"/>
<role rolename="manager-script"/>
<role rolename="manager-jmx"/>
<role rolename="manager-status"/>
<user username="admin" password="admin" roles="manager-gui, manager-script, manager-jmx, manager-status"/>
```

after updating `tomcat-users.xml`

now go to webapps and comment the locahost
apache9>webapps>manager>META-INF>context.xml

```
<!-- <CookieProcessor className="org.apache.tomcat.util.http.Rfc6265CookieProcessor" sameSiteCookies="strict" />
  <Valve className="org.apache.catalina.valves.RemoteAddrValve"
allow="127\.\d+\.\d+\.\d+|::1|0:0:0:0:0:0:0:1" /> -->
```

Now goto apache9>bin and start the tomcat server 

`sh startup.sh`
