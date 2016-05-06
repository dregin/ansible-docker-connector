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

### Current output
```bash
➜  ansible-docker-connector git:(master) ansible-playbook hostnames.yml -i hosts -vvvv

Using /Users/user.name/.ansible.cfg as config file
Loaded callback default of type stdout, v2.0

PLAYBOOK: hostnames.yml ********************************************************
1 plays in hostnames.yml

PLAY [docker] ******************************************************************

TASK [hostname : print hostname] ***********************************************
task path: /Users/user.name/Projects/ansible-docker-connector/roles/hostname/tasks/main.yml:2
ESTABLISH DOCKER CONNECTION FOR USER: None
<slave_0001> EXEC ['/usr/local/bin/docker', 'exec', '-u', None, '-i', u'slave_0001', '/bin/sh', '-c', u"/bin/sh -c 'LANG=en_US.UTF-8 LC_ALL=en_US.UTF-8 LC_MESSAGES=en_US.UTF-8 /usr/bin/python'"]
fatal: [slave_0001]: FAILED! => {"changed": false, "failed": true, "invocation": {"module_name": "command"}, "module_stderr": "", "module_stdout": "", "msg": "MODULE FAILURE", "parsed": false}

NO MORE HOSTS LEFT *************************************************************
        to retry, use: --limit @hostnames.retry

PLAY RECAP *********************************************************************
slave_0001                 : ok=0    changed=0    unreachable=0    failed=1
```
