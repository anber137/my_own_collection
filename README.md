# Домашнее задание к занятию "08.04 Создание собственных `modules`"

## 4. Проверьте module на исполняемость локально.

## 5. Напишите single task playbook и используйте module в нём.

### При решении всех пунктов Повторил, что было в лекции

```YAML
---
- name: Assert create_file_module
  hosts: localhost
  tasks:  
   - name: Create file
     create_file:
       path: ./another_one.txt
       content: "any any"
```

## 6. Проверьте через playbook на идемпотентность.

```
1. 

localhost                  : ok=2    changed=1    unreachable=0    failed=0    skipped=0    rescued=0    ignored=0

ok: [localhost]


2. 

PLAY RECAP ***************************************************************************************************************************
localhost                  : ok=2    changed=0    unreachable=0    failed=0    skipped=0    rescued=0    ignored=0
```

## 7-15

После установки `collection`:

```
ansible-playbook site.yml 
[WARNING]: You are running the development version of Ansible. You should only run Ansible from "devel" if you are modifying the
Ansible engine, or trying out features under development. This is a rapidly changing source of code and can become unstable at any
point.
[WARNING]: Found both group and host with same name: ubuntu

PLAY [test] **************************************************************************************************************************

TASK [Gathering Facts] ***************************************************************************************************************
ok: [localhost]

TASK [test collection] ***************************************************************************************************************
changed: [localhost]

PLAY RECAP ***************************************************************************************************************************
localhost                  : ok=2    changed=1    unreachable=0    failed=0    skipped=0    rescued=0    ignored=0   
```

