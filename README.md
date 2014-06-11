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
Example Firewall and Webserver container chains using docker

fw: implements example firewall that directly installs the firewall rule in the host's iptable. Hence, the traffic never hits the fw container.

docker-node-hello: a simple node.js server. This webserver has the front-end fw above. Traffic access to this node.js is protected by the firewall.
