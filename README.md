# Dr - my DockeR commands

Most docker commands work on the docker IDs. I find this cumbersome,
so I've written a set of commands that lets you pass the name of the
container instead.

Normally, only parts of the name is needed, i.e. instead of doing
`drshell docker_nginx_1` to get a shell on the `docker_nginx_1`
container, you can just type `drshell nignx`.

## Examples

### drshell

Get a shell in a container by name:
```shell
$ drshell redis
root@36b953823ecf:/data#
```

### drps

An improved `docker ps` command that include the IP of the containers:
```shell
$ drps
CONTAINER ID  IMAGE                           CREATED              IP           PORTS                                                                                                                         NAMES
e13b7adfb7cb  skybert/foo                     2018-03-21T12:15:32  172.19.0.9   map[8680/tcp:[map[HostPort:8680 HostIp:0.0.0.0]] 8681/tcp:[map[HostIp:0.0.0.0 HostPort:8681]]]                                /docker_cue_um_1
2461d54ca9d0  gluufederation/nginx:latest     2018-03-21T12:15:32  172.19.0.8   map[443/tcp:[map[HostIp:0.0.0.0 HostPort:9981]] 80/tcp:[map[HostIp:0.0.0.0 HostPort:9980]]]                                   /docker_um_1
91a36134935d  gluufederation/oxtrust:latest   2018-03-21T12:15:32  172.19.0.7   map[8080/tcp:<nil>]                                                                                                           /docker_oxtrust_1
e2e15013548b  gluufederation/oxauth:latest    2018-03-21T12:15:31  172.19.0.6   map[8080/tcp:<nil> 9005/tcp:[map[HostIp:0.0.0.0 HostPort:9005]]]                                                              /docker_oxauth_1
6bb857c81f41  gluufederation/openldap:latest  2018-03-21T12:15:31  172.19.0.5   map[1636/tcp:<nil>]                                                                                                           /docker_ldap_1
b148c7c2df3c  consul                          2018-03-21T12:15:30  172.19.0.3   map[8302/tcp:<nil> 8302/udp:<nil> 8500/tcp:<nil> 8600/tcp:<nil> 8600/udp:<nil> 8300/tcp:<nil> 8301/tcp:<nil> 8301/udp:<nil>]  /docker_consul_1
36b953823ecf  redis                           2018-03-21T12:15:30  172.19.0.2   map[6379/tcp:<nil>]                                                                                                           /docker_redis_1
```

### drip

Get the IP of a container by name.

```shell
$ drip oxauth
172.19.06
```

### drlog
Tail the log of a container by name.

```shell
$ drlogs oxauth
```


## Contribute

Please do, fork the repo and create a pull request.

## Licence

See [LICENSE](LICENSE).
