## sandbox env for docker swarm

e.g. to init swarm
```bash
vagrant up
vagrant ssh swarm-node-0
docker swarm init --advertise-addr 10.100.192.200
```
