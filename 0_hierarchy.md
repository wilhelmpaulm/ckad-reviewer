# Hierarchy

## Nodes

- also known as minions
- is a machine, physical or virtual

## Cluster

- set of nodes grouped together

## Master

- is a node with kubernetes installed in it
- watches over the other "worker nodes" and decides where the load goes to when one node failes

## Components

- API server
    - what we use to interact with the kubernetes server
- etcd
    - distributed reliable key value store to store data used to manage the cluster
    - responsible for implementing logs
- kubelet
    - the agent that runs on each node on the cluster
    - signals the master node
- container runtime
    - underlying software used to run containers
    - usually docker
- controller
    - the brain behind orchestration
    - watches when nodes fail and revives them
- scheduler
    - responsible for distributing work or containers across multiple nodes




