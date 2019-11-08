# REDIS ADVANCES

Author: CongVm

## Introduction

This project is to setup and test some advanced built-in mechanism in Redis which is used in many projects.


## Installations

```
pip install redis redis-py-cluster

Ubuntu: sudo apt install redis

# Redis==5.0.6 in my machine

```

## Redis Sentinel

Maybe you need modify script to be appropriate to you cases.
`cd sentinel`

- Start Redis DB: `./start_all_redis.sh`

- Start Redis Sentinel: `./start_all_sentinel.sh`

To freeze one of Redis DB:  
    `redis-cli -p <redis-port>  DEBUG sleep 30`

Open `log` in node-xxx to view the failover, voting, switch-master ..


## Redis Cluster

Start a redis nodes/instances in distint servers.

You can use `code` in `cluster` folder

```
cd cluster/cluster-3000x

./create-cluster start  # Create 6 redis instances in same machine

./create-cluster create # Choose the 3 first redis instances to be master and the rest is slaves in order. In this time, failover mechanism will be start and action when master downs.
```

```
cd jupyter
jupyter-lab
```

And enjoy the example.

## Reference

1. https://redis.io/topics/sentinel

2. https://github.com/andymccurdy/redis-py/blob/master/redis/sentinel.py

3. https://pypi.org/project/redis-py-cluster/
