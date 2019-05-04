# citc-enable-ptm

Enables PTM in CiTC from blank slate

Psuedo code for this playbook:

* bring up all spine interfaces
* bring up all leaf interfaces
* copy the topology.dot file to all leaf and spine switches
* restart the ptmd service to instantiate PTM on all leaf and spine
* install LLDP and SNMP on all the servers
* start LLDP and SNMP on all the servers
* bring up eth1 and eth2 interfaces on all the servers

```bash
cumulus@oob-mgmt-server:~$ git clone https://github.com/ls62-dev/citc-enable-ptm
Cloning into 'citc-enable-ptm'...
remote: Enumerating objects: 57, done.
remote: Counting objects: 100% (57/57), done.
remote: Compressing objects: 100% (46/46), done.
remote: Total 57 (delta 17), reused 50 (delta 10), pack-reused 0
Unpacking objects: 100% (57/57), done.
Checking connectivity... done.
cumulus@oob-mgmt-server:~$ cd citc-enable-ptm
cumulus@oob-mgmt-server:~/citc-enable-ptm$ ansible-playbook cp_topo.yml
```

This command will validate PTM in the fabric, run it after the playbook.

`ansible leaf:spine -a ptmctl`
