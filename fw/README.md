
# A simple firwewall that installs drop rule for nodetest in host's iptables
# https://docs.google.com/presentation/d/1MfteHfaGLMWZRxLEx4vYE5ZB2v9MYtoFX6Mj7B2TGKM/edit?usp=sharing 

## Prerequisites

- ubuntu && iptables

## Getting Started
-   Build docker image:
        # docker build -t iptablesfw .


-   Run app:
        # docker run --net="host" --privileged iptablesfw


-  Ensure the drop fw rule is installed in the host's iptables

root@ubuntu:/mnt/hgfs/Downloads/dockerhackathon# iptables -L -v -n
Chain INPUT (policy ACCEPT 11177 packets, 5048K bytes)
 pkts bytes target     prot opt in     out     source               destination         
    0   0 DROP       tcp  --  *      *       0.0.0.0/0            0.0.0.0/0            tcp dpt:49000


-   Install `curl`:

        sudo apt-get install curl


-   Test app using the port in previous step, e.g. 49000:

        curl localhost:<port>

        # Example
        # curl localhost:49000

    It should not allow access to webserver and the packet counters on iptables should increase

root@ubuntu:/mnt/hgfs/Downloads/dockerhackathon# iptables -L -v -n
Chain INPUT (policy ACCEPT 11177 packets, 5048K bytes)
 pkts bytes target     prot opt in     out     source               destination         
    3   180 DROP       tcp  --  *      *       0.0.0.0/0            0.0.0.0/0            tcp dpt:49000



## Acknowledgements

Many thanks to @dotCloud team for docker.

