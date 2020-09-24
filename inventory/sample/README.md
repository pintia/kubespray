sample is changed to patest dev env config
---
we should use offline deploy:

`ansible-playbook cluster.yml -b -i inventory/sample/inventory.ini -e "{'download_run_once': true}" -e "{'download_localhost': true}"`

optional:

`-e "{'upgrade_cluster_setup': true}"`
