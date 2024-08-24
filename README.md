# Requirement

AlmaLinux8<br>
Ipv6 /64

First update ulimit<br>
vi /etc/security/limits.conf<br>
add these two lines and restart the server<br>
  \*  tsoft  nofile  65535<br>
  \*  hard  nofile  65535

then login again and do below steps
<br>
yum update -y<br>
yum -y install curl wget nano make<br>

wget https://raw.githubusercontent.com/jackalsoft/multiipv6/main/install.sh

chmod +x /root/install.sh<br>
bash /root/install.sh {IPV6Value}

Example :
IPV6Value can be taken from IPV6Range.
Consider this IPV6Range 2600:3c06:e001:47::/64<br>
Only cut 4, : delimited range 2600:3c06:e001:47 and pass it as param. <br>
bash /root/install.sh 2600:3c06:e001:47<br>

After installation dowload the file proxy.zip
File structure: IP4:PORT:LOGIN:PASS
You can use this online util to change proxy format as you like


Finally allow the port ranges in firewall<br>
firewall-cmd --permanent --zone=public --add-port=10000-11000/tcp
