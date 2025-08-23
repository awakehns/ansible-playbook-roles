# Домашнее задание к занятию 4 `«Работа с roles»` - `Демин Герман`

### Задание 1

```
ansible --version

nano requirements.yml

ansible-galaxy install -r requirements.yml -p roles

ansible-galaxy role init vector-role
```

Скачана роль
![role-1](/img/role-1.png)

```
ansible-galaxy role init roles/lighthouse-role

ansible-galaxy role init roles/vector-role
```

Проинициализированы новые роли
![roles](/img/roles.png)

Прописал все файлы в ролях.

`nano site.yml`

```                                                
---
- hosts: all
  become: true
  roles:
    - { role: clickhouse, when: ansible_distribution != "Archlinux" }
    - vector-role
    - lighthouse-role
```

Старт проекта
![start](/img/start.png)
