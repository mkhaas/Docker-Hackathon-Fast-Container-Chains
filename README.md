Docker-Hackathon-Fast-Container-Chains
======================================
Problem Statement
=================

[1]  Companies use containers as efficient, lightweight entities to package their services
[2] Users chain these best-of-breed container services to provide value-added offerings to customers
[3] Network layer services require low latency implementation
e.g. Firewalls and Load Balancers

Solution
========
Fast Container Chains  
See attached containerchains.pdf

Implementation
==============

Example:  Firewall and Webserver container chains using docker

fw: implements simple firewall that directly installs the firewall rule directly in the host's iptable. Hence, the traffic never hits the fw container.

docker-node-hello: a node.js server. The fw container above controls traffic access to this node.js server.

In the above example, 

[1] First run only the nodetest container --> nodetest is port-natted on host 49000. All traffic is allowed on port 49000

[2] Next, run fw container. It installs "drop traffic on port 49000" rule directly in the host's ip table. All nodetest traffic is drop at the host (does not reach the fw container).
