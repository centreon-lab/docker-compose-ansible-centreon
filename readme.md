Docker compose Tests
====================

Necessary
---------

 - Docker compose (https://docs.docker.com/compose/)

How to use
----------

Git clone these repository
```bash
cd work
git clone https://github.com/centreon-lab/docker-compose-ansible-centreon.git
```

Do run docker-compose to deploy the Tests
```bash
cd work/docker-compose-ansible-centreon
docker-compose up
```

Network configuration (If necessary, change the values in `docker-compose.yml` file)

 - 192.168.88.0/24
