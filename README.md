# Stanford CoreNLP docker
Dockerfile for the Stanford CoreNLP server.

## Getting started
To build the docker image for the Stanford CoreNLP Server:  
```
cd docker/stanford-corenlp-server
docker build -t corenlp .
```

By editing the Dockerfile you can also:
- Set the number of threads using the THREADS variable
- Set the ammount of ram using the JAVA_XMX variable
- Set the port number using the PORT variable

By default the server uses 2 threads, up to 2GB of memory, and runs on port 9000.

## Start a CorenNLP server container
You can start a CoreNLP Server container using:  
`docker run -p 9000:9000 corenlp`

## Example
To annotate the sentence “the quick brown fox jumped over the lazy dog” with part of speech tags run:

`curl --data 'The quick brown fox jumped over the lazy dog.' 'http://localhost:9000/?properties={%22annotators%22%3A%22tokenize%2Cssplit%2Cpos%22%2C%22outputFormat%22%3A%22json%22}' -o -`

## Project repository
https://github.com/evanlal/stanford-corenlp-docker

## Author
**Evan Lalopoulos** - [evanlal](https://github.com/evanlal)

## License
Written by Evan Lalopoulos <evan.lalopoulos.2017@my.bristol.ac.uk>    
Copyright (C) - All rights reserved.  
Unauthorized copying is strictly prohibited. 
