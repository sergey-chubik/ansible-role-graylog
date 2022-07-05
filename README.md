Ansible Role: GrayLog Server
=========

Эта роль установит GrayLog Server версии 4.0 на CentOS 7.

Requirements
------------

None.

Role Variables
--------------

Доступные переменные перечислены ниже вместе со значениями по умолчанию в файле **defaults/main.yml**.
Установите свои значения пароля для кластера Graylog:
```
- graylog_password_secret: sbTFvW1eaXa1xJ29UqIuoU9r6e8V3d9r
```

Задайте хеш-пароль для пользователя root для регистрации в веб-интерфейсе сервера Graylog (сгенерировать его можно командой: `echo -n guinguin | sha256sum`):
```
- graylog_root_password_sha2: e50cd08ec046bc5fc0a4ca84c9b06eb6293787bd5e8eac73da95de6b38a16be9
```

Dependencies
------------

Также необходимо открыть следующие порты и службы в firewall:
```
- service: http
- port: 1514/udp
- port: 9996/udp
```

Example Playbook
----------------

Including an example of how to use your role (for instance, with variables passed in as parameters) is always nice for users too:

    - hosts: servers
      roles:
         - graylog

License
-------

BSD

Author Information
------------------

Chubik Sergey.
