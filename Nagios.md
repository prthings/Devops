1. Login to the AWS account.
2. Create two instances one is for “nagios_server” and another for “remote_server” client.
 AMI --> Linux 2
 Instance type --> t2.micro
 Security Group --> all traffic
 connect --> mobaxterm

3. Connect to the nagios_server and install or configure the nagios.
a) To install and configure the nagios_server follow the below steps:
$ vi nagios.sh
yum -y install httpd php gcc glibc glibc-common wget perl gd gd-devel unzip zip
useradd nagios
groupadd nagcmd
usermod -a -G nagcmd nagios
usermod -a -G nagcmd apache
cd /tmp/
wget https://assets.nagios.com/downloads/nagioscore/releases/nagios-4.3.2.tar.gz
tar -zxvf nagios-4.3.2.tar.gz
cd /tmp/nagios-4.3.2
./configure --with-nagios-group=nagios --with-command-group=nagcmd
make all
make install
make install-init
make install-config
make install-commandmode
make install-webconf
make install-exfoliation
systemctl restart httpd
systemctl enable httpd
htpasswd -c /usr/local/nagios/etc/htpasswd.users nagiosadmin
$ sh nagios.sh
New password:<Enter the password>
Re-type new password:<Retype the same password>

4. Copy the “Public_IP” of the instance and paste it in the chrome along with /nagios
$ <Public_IP>/nagios

Note:
You can see the nagios GUI but you cannot access other things to access entire nagios please follow below steps

5. Now we have to install the nagios plugin in the nagios_server to do it follow below steps
$ vi nagios_plugin.sh
cd /tmp
wget https://nagios-plugins.org/download/nagios-plugins-2.2.1.tar.gz
tar -zxvf nagios-plugins-2.2.1.tar.gz
cd /tmp/nagios-plugins-2.2.1/
./configure --with-nagios-user=nagios --with-nagios-group=nagios
make
make install
/usr/local/nagios/bin/nagios -v /usr/local/nagios/etc/nagios.cfg
service nagios start
chkconfig nagios on
$ sh nagios_plugin.sh

Note:
Now go and refresh the nagios website you will be seeing that nagios is running and working fine
---------------------------------------------------------------------------------------
ON REMOTE SERVER / CLIENT SERVER
--------------------------------------------------------------------------------------
6. Connect the instance of remote_monitoring
7. Install nagios plugin

8. Install NRPE plugin
a) To install the nagios plugin and NRPE plugin follow the below steps
$ rpm -ivh https://dl.fedoraproject.org/pub/epel/epel-release-latest-7.noarch.rpm
$ yum install -y nrpe nagios-plugins-all

9. Go to the “nrpe.cfg” file and add the Public_IP in the sectioned called allowed hosts as shown below, In the same file you can also see there are commands to check several services of the remote server
$ vi /etc/nagios/nrpe.cfg
allowed_hosts=127.0.0.1,<public_ip of the nagios_server>

10. Start the NRPE service by typing the below command
$ systemctl start nrpe

11. Enable the NRPE service by typing the below command
$ systemctl enable nrpe
--------------------------------------------------------------------------------------------
ON NAGIOS SERVER
--------------------------------------------------------------------------------------------
12. Install the NRPE plugin
a) To install follow the steps given below
$ rpm -ivh https://dl.fedoraproject.org/pub/epel/epel-release-latest-7.noarch.rpm
$ yum -y install nagios-plugins-nrpe

13. Go to the file given below and add the or comment the section mentioned below
$ vi /usr/local/nagios/etc/nagios.cfg
cfg_dir=/usr/local/nagios/etc/servers <-- uncomment

14. Create one folder called servers in the below mentioned path
$ mkdir /usr/local/nagios/etc/servers

15. Go to commands.cfg file and add the following Nagios command definition to the file.
$ vi /usr/local/nagios/etc/objects/commands.cfg
# .check_nrpe. command definition
define command {
command_name check_nrpe
command_line /usr/lib64/nagios/plugins/check_nrpe -H $HOSTADDRESS$ -t 30 -c $ARG1$
}

16. Now go to the servers directory that already created in the 15th step , create one file with .cfg extension and add the content mentioned below
$ cd /usr/local/nagios/etc/servers
$ vi hosts.cfg
define host{
use linux-server
host_name Jspiders
alias Jspiders
address 13.233.95.15
}
define hostgroup{
hostgroup_name linux-server
alias Linux Servers
members Jspiders
}
define service{
use local-service
host_name Jspiders
service_description Current Users
check_command check_nrpe!check_users
}
define service{
use local-service
host_name Jspiders
service_description Total Processes
check_command check_nrpe!check_total_procs
}
define service{
use local-service
host_name Jspiders
service_description Current Load
check_command check_nrpe!check_load
}

17. Check is there any errors in the nagios server by typing the command given below
$ /usr/local/nagios/bin/nagios -v /usr/local/nagios/etc/nagios.cfg

18. Restart the Nagios by using the command given below
$ systemctl restart nagios

19. Now go and check in Nagios website your host will be added but it will be down so we have to add the ping security group in the nagios_server and remote_hosting server security groups
>ALL ICMP - IPV4
