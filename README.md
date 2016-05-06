# ansible-docker-connector
Testin ansible's docker connector with Docker for Mac beta

## Spin up docker container
```bash
docker-compose up -d
```

## Run ansible playbook
```bash
ansible-playbook hostnames.yml -i hosts
```
