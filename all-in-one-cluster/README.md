# All In One Cluster

This scenario deploys the following topology:

  * 1 DB node
  * 1 Redis node
  * 3 pulp (all services) nods
  * 1 HAProxy node


## How to deploy

```
# vagrant up
# vagrant ssh-config > ssh-config
# git clone https://github.com/pulp/pulp_installer
# ansible-galaxy install -r pulp_installer/requirements.yml
# ansible-galaxy install chouseknecht.ansible_galaxy_config
# ansible-playbook -i inventory playbook.yml -e @vars.yml
```

**Note**: Currently there is a small issue with how Redis behaves, if the first run fails with a `Connection Timed Out` when restarting redis, please simply retrigger the `anssible-playbook` command.
