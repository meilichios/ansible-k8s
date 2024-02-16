# ANSIBLE-K8S deployment scripts

## Description
Installs vanilla K8S + Calico with VXLAN.

## Files
* vars.yml
* wipe_hv.yml
* domains.ini
* bootstrap.yml

## Dependencies
### Local Dependencies
* git
* python3
* ansible-core 2.1x

```bash
ansible-galaxy collection install community.general 
```
* community.general.posix
```bash
ansible-galaxy collection install community.posix
```
### Remote Dependencies
* Linux 5.4.0-155-generic #172-Ubuntu SMP Fri Jul 7 16:10:02 UTC 2023 x86_64 x86_64 x86_64 GNU/Linux


## Installation
0. Clone the repository
1. Configure / double check domains.ini vars.yml
2. Wipe the target VMs
3. Bootstrap the cluster
```bash
ansible-playbook -u super -kK -i ../inventories/domains.ini bootstrap.yml
```
All *worker* nodes will be joined and labeled as 'worker=True' automatically.

## Authors

* VDistefano

## License

This project is licensed under the MIT License