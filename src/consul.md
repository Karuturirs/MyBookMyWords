# 							Consul

____

## Installation

Download consul from the link https://www.consul.io/downloads.html

Make sure that the `consul` binary is available on your `PATH`. You can check the locations available on your path by running this command.

```shell
$ echo $PATH
/usr/local/bin:/usr/bin:/bin:/usr/sbin:/sbin
```

The output is a list of locations separated by colons. You can make Consul available by moving the binary to one of the listed locations, or by adding Consul's location to your `PATH`.



### Check installation 

```shell
$ consul
usage: consul [--version] [--help] <command> [<args>]

Available commands are:
    agent          Runs a Consul agent
    event          Fire a new event

...
```

## Starting the Agent

Start the Consul agent in development mode.

```shell
$ consul agent -dev
```

## Datacenter Members

```shell
$ consul members
Node      Address         Status  Type    Build  Protocol  DC   Segment
A501004  127.0.0.1:8301  alive   server  1.4.3  2         dc1  <all>
```

## Stopping the Agent

Stop the Consul agent by using the `consul leave` command. This will gracefully stop the agent, causing it to leave the Consul datacenter and shut down.

```shell
$ consul leave
Graceful leave complete
```

```shell
$ docker run -d --name consul --restart on-failure:5 -p 8500:8500 consul:latest
```

