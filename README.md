Active_Directory_Domain
=========

Creates a Active Directory Domain on Windows Server 

Requirements
------------

Requires WinRM

pip install winrm

Role Variables
--------------

Role takes following vars

safemodepw = Active Directory Safe Mode Password

domain = Domain name for Active Directory

Dependencies
------------

None

Example Playbook
----------------

```ansible

- hosts: tag_ansible_dc01
  name: Configure Active Directory on DC01
  vars:
    ansible_user: "{{ azurevmuser }}"
    ansible_password: "{{ azurevmpw }}"
    ansible_port: 5985
    ansible_connection: winrm
    ansible_winrm_transport: ntlm
    ansible_winrm_message_encryption: always
  tasks:
    - name: Configure AD
      include_role:
        name: active-directory-domain
      vars:
        domain: "testdomain.local"
        safemodepw: "SomePassword"
```

License
-------

BSD

Author Information
------------------

Jesper Berth
