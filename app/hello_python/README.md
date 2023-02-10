# Hello world - containerized rest endpoint
This is a simple hello-world application with docker support.

## Build an image with docker compose
```
$ docker compose build
```


## Deploy with docker compose

```
$ docker compose up -d
[+] Building 1.1s (16/16) FINISHED
 => [internal] load build definition from Dockerfile                                                                                                                                                                                       0.0s
    ...                                                                                                                                         0.0s
 => => naming to docker.io/library/hello_python_web                                                                                                                                                                                               0.0s
[+] Running 2/2
 ⠿ Network hello_python_default  Created                                                                                                                                                                                                          0.0s
 ⠿ Container hello_python-1  Started
```

## Expected result

Listing containers must show one container running and the port mapping as below:
```
$ docker compose ps
NAME                COMMAND             SERVICE             STATUS              PORTS
hello_python-web-1         "python3 app.py"    web                 running             0.0.0.0:8000->8000/tcp
```

After the application starts, navigate to `http://localhost:8000` in your web browser or run:
```
$ curl localhost:8000
Hello World!
```

Stop and remove the containers
```
$ docker compose down
```