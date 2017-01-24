# ansible-mlnx-onie-recovery

Ansible playbook to deploy a PXE environment for ONIE recovery on Mellanox switches.
Tested on Mellanox Spectrum switches (SN2100, SN2700, SN2410).

Prerequisites
-------------------
* Server/VM with Ubuntu Linux 16.x
* Ansible 2.x
* ONIE recovery file (i.e: onie-recovery-x86_64-kvm_x86_64-r0.iso )
* ONIE updater file (i.e: onie-updater-x86_64-mlnx_x86-r5_0_1410.1410.bin )

Usage
-------------------

* Login as **root**
* **git clone https://github.com/kvadrage/ansible-mlnx-onie-recovery.git**
* **cd ansible-mlnx-onie-recovery**
* **mv *.iso roles/pxe/files && mv *.bin role/pxe/files**
* Edit vars in **roles/pxe/vars/main.yaml**
* Run playbook: **ansible-playbook pxe.yml**
* PXE environment for ONIE recovery is up and ready!

After installation
-------------------
* connect a switch mgmt0 port to the same VLAN, where PXE server is connected
* ensure there is no other DHCP servers in this VLAN
* connect to a switch console and boot it
* configure network boot in switch BIOS (contact Mellanox for additional instructions)
* wait the switch to boot into the PXE and recover ONIE partition
