sample is changed to patest prod env config
---
we should use offline deploy:

`ansible-playbook cluster.yml -b -i inventory/sample/inventory.ini -e "{'download_run_once': true}" -e "{'download_localhost': true}"`

optional:

`-e "{'upgrade_cluster_setup': true}"`

upgrade
---
`ansible-playbook upgrade-cluster.yml -b -i inventory/sample/inventory.ini -e "{'download_run_once': true}" -e "{'download_localhost': true}"`

upgrade kernel
---
`ansible -i inventory/sample/inventory.ini all -a "apt-get update"`
`ansible -i inventory/sample/inventory.ini all -a "apt-get install -y linux-generic-hwe-18.04"`

scale up
---
`ansible-playbook -b -v -i inventory/sample/inventory.ini scale.yml -e "{'download_run_once': true}" -e "{'download_localhost': true}"`
