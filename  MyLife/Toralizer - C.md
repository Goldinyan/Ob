command line client for connecting to the tor privacy network, when you run a cli command for running a network call

```bash
bash$ curl http://12.34.45.67
```

The connect function, where the programm establishes a tcp connection and then the communaction begins is invoked to connect the client to the server 

with this tool you will write *toralize* in front of every function that makes a network call

```bash
bash$ toralize curl http://12.34.45.67
```

it will intercept any function and will run our function instead, like *my_connect()*, the traffic will be redireced to a local proxy server which is a part of the tor network
so first connected to the tor network and then to the destination server , masking you identity, helping you to stay privat 