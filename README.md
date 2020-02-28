System created with kubeup and where `inventory` is a link to the
vagrant inventory file:

```
/path/to/VM/.vagrant/provisioners/ansible/inventory/vagrant_ansible_inventory
```

```
$ ansible-playbook -i inventory site.yml

PLAY [lpabon-k8s-1-node0] ****************************************************************************************************************

TASK [Gathering Facts] *******************************************************************************************************************
ok: [lpabon-k8s-1-node0]

TASK [common : get token from kubernetes] ************************************************************************************************
changed: [lpabon-k8s-1-node0]

TASK [common : set_fact] *****************************************************************************************************************
ok: [lpabon-k8s-1-node0]

TASK [common : checking cluster status] **************************************************************************************************
changed: [lpabon-k8s-1-node0]

TASK [common : setup pxctl context] ******************************************************************************************************
changed: [lpabon-k8s-1-node0]

TASK [common : check volume exists] ******************************************************************************************************
fatal: [lpabon-k8s-1-node0]: FAILED! => {"changed": true, "cmd": "/opt/pwx/bin/pxctl volume list | grep myvol", "delta": "0:00:00.085329", "end": "2020-02-28 08:50:50.594358", "msg": "non-zero return code", "rc": 1, "start": "2020-02-28 08:50:50.509029", "stderr": "", "stderr_lines": [], "stdout": "", "stdout_lines": []}
...ignoring

TASK [common : volume create] ************************************************************************************************************
changed: [lpabon-k8s-1-node0]

TASK [common : volume inspect] ***********************************************************************************************************
changed: [lpabon-k8s-1-node0]

TASK [common : delete volume] ************************************************************************************************************
changed: [lpabon-k8s-1-node0]

PLAY RECAP *******************************************************************************************************************************
lpabon-k8s-1-node0         : ok=9    changed=7    unreachable=0    failed=0    skipped=0    rescued=0    ignored=1   
```
