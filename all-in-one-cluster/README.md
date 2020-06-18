# All In One Cluster

This scenario deploys the following topology:

  * 1 DB node
  * 1 Redis node
  * 3 pulp (all services) nods
  * 1 HAProxy node


## How to deploy

```
# git clone https://github.com/pulp/pulp_installer
# ansible-galaxy install -r pulp_installer/requirements.yml
# ansible-galaxy install chouseknecht.ansible_galaxy_config
# mkdir -p pulp && chown -R 1001:1001 pulp
# vagrant up --no-parallel
# vagrant ssh-config > ssh-config
# ansible-playbook -i inventory playbook.yml -e @vars.yml
```

When this finishes, use any `pulp[01:03]` IP or the `haproxy01` to reach your interface. Here the Galaxy interface has been added to provide an easy way to test the scenario.

**Note**: Currently there is a small issue with how Redis behaves, if the first run fails with a `Connection Timed Out` when restarting redis, please simply retrigger the `anssible-playbook` command.
