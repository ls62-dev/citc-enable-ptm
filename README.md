# citc-enable-ptm
Enables PTM in CiTC from blank slate

Psuedo code for this playbook:

* copy the topology.dot file to all leaf and spine switches
* restart the ptmd service to instantiate ptm on all leaf and spine
* install LLDP and SNMP on all the servers
* start LLDP and SNMP on all the servers
* bring up eth1 and eth2 interfaces on all the servers

This command will validate PTM in the fabric, run it after the playbook.

`ansible leaf:spine -a ptmctl`
