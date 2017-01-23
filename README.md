# ansible-mlnx-onie-recovery

Ansible playbook to deploy a PXE environment for ONIE recovery on Mellanox switches

Prerequisites
-------------------
* Ansible 2.x
* ONIE recovery file (i.e: onie-recovery-x86_64-kvm_x86_64-r0.iso )
* ONIE updater file (i.e: onie-updater-x86_64-mlnx_x86-r5_0_1410.1410.bin )

Usage
-------------------

* Install Ubuntu 14
* Login as **root**
* git clone git://github.com/cloneko/ansible-pxe.git
* cd ansible-mlnx-onie-recovery
* mv *.iso role/pxe/files && mv *.bin role/pxe/files
* Run playbook: ansible-playbook pxe.yml
