ansible-role-vyos-interface
=========
VyOSのインターフェース設定の追加、削除を行います。

Requirements
------------

Ansible version >= 2.2

(connection: network_cli 利用時 >=2.5)

Role Variables
--------------

|変数名     |内容                        |
|-----------|----------------------------|
|vyos_config|VyOSへの設定内容を定義します|

### vyos_config
```yml
vyos_config:
  connection:
    host:     vyos.example.com
    username: vyos
    password: vyos-password

  interfaces:
    ethernet:
      eth0:
        address: dhcp

    dummy:
      dum0:
        address: 10.2.0.1/24

      dum1:
        address: 10.2.1.1/24

  del_interfaces:
    dummy:
      dum0:
        address: 10.2.0.2/24

      dum1:
        address: 10.2.1.2/24
```

Example Playbook
----------------
```yml
    - hosts: servers
      roles:
         - { role: ansible-role-vyos-interface }
```

License
-------
MIT