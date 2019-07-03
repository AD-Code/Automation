Role Name
=========

This ensures Prism is configured to your desired state.

Requirements
------------

Requires a local cluster admin account on each prism instance to make any changes and port 9440 open through any firewalls.

Role Variables
--------------

This role makes use of the defaults/main.yml to house almost all configurations.  This role was developed with the following inventory format in use to allow for flexability 

/vars<br>
  * /Location1<br>
  * 	main.yml #holds specific information for location1<br>
  * 	pc.yml #holds Prism Central specific data<br>
  * 	pe.yml #holds Prism Element specific data<br>
  * /Location2<br>
  * 	main.yml<br>
  * 	pc.yml<br>
  * 	pe.yml<br>
  * /inventory<br>
  * 	clustername.yml<br>
  * /purpose<br>
  * 	vdi.yml<br>
  * 	vsi.yml<br>
  * creds.yml<br>
  * main.yml<br>


Dependencies
------------

No dependencies on other roles or ansible functions

Example Playbook
----------------

ansible-playbook configure_cluster -e cluster_name="clustername"

---
- hosts: localhost

  tasks:
  
    - name: configure cluster to desired state
      include_role:
        name: nutanix_cluster_baseline
        tasks_from: configure_cluster/main.yml

License
-------

BSD

Author Information
------------------

An optional section for the role authors to include contact information, or a website (HTML is not allowed).
