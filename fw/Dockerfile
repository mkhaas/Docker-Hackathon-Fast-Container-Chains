# Building a FW container; Add a drop rule for webserver

FROM    ubuntu

RUN apt-get update; apt-get install -y iptables

#Add Firewall rule to drop the web-traffic 
CMD  iptables -A INPUT -p tcp --dport 49000 -j DROP  
