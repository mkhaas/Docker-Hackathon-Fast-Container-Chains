#Fast Container Chaining  https://docs.google.com/presentation/d/1MfteHfaGLMWZRxLEx4vYE5ZB2v9MYtoFX6Mj7B2TGKM/edit?usp=sharing 

# Node.js Hello World

#
Node.js Hello World on CentOS using [docker][].

## Prerequisites

- [Node.js & npm][node-js-download]

## Getting Started
-   Build docker image:
        # docker build -t nodetest .


-   Run app:
        # docker run -p 49000:8080 -d nodetest

-   Install `curl`:

        sudo apt-get install curl


-   Test app using the port in previous step, e.g. 49000:

        curl localhost:<port>

        # Example
        # curl localhost:49000

    It should print `Hello Docker Hackathon World` to the console.

## Acknowledgements

Many thanks to @dotCloud team for docker.


[node-js-download]: http://nodejs.org/download/
[docker]: http://docker.io
