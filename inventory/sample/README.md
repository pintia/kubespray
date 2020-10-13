changed to deployment for patest dev cluster.
---

we should use offline deploy:

ansible-playbook cluster.yml -b -i inventory/patest/inventory.ini -e "{'download_run_once': true}" -e "{'download_localhost': true}" -e "{'upgrade_cluster_setup': true}"
