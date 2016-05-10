# ansible-docker-connector
Testing ansible's docker connector with Docker for Mac beta.
When run without ansible_user=root set in the inventory, this simple playbook fails.

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
➜  ansible-docker-connector git:(master) ✗ ansible --version
ansible 2.0.2.0
  config file = /Users/user.name/Projects/ansible-docker-connector/ansible.cfg
  configured module search path = Default w/o overrides
➜  ansible-docker-connector git:(master) ansible-playbook hostnames.yml -i hosts

PLAY [docker] ******************************************************************

TASK [setup] *******************************************************************
fatal: [slave_0001]: FAILED! => {"failed": true, "msg": "failed to resolve remote temporary directory from ansible-tmp-1462914143.95-154306547084230: `( umask 22 && mkdir -p \"` echo $HOME/.ansible/tmp/ansible-tmp-1462914143.95-154306547084230 `\" && echo \"` echo $HOME/.ansible/tmp/ansible-tmp-1462914143.95-154306547084230 `\" )` returned empty string"}

NO MORE HOSTS LEFT *************************************************************
        to retry, use: --limit @hostnames.retry

PLAY RECAP *********************************************************************
slave_0001                 : ok=0    changed=0    unreachable=0    failed=1
```
