Filebeat role
=========

Роль для установки Filebeat на хостах с ОС: Debian, Ubuntu, CentOS, RHEL.

Requirements
------------

Поддерживаются только ОС семейств debian и EL.

Role Variables
--------------

| Variable name | Default | Description |
|----------------|----------|-------------------------|
| filebeat_version | "7.14.0" | Filebeat какой версии будет установлен |
| filebeat_install_type | remote | Тип установки: remote или local |
| elasticsearch_hosts | `"[\"http://{{ ansible_facts['default_ipv4']['address'] }}:9200\"]"` | Строка в формате JSON-массива, в элементах которого надо указать хосты Elascticsearch. Значение по умолчанию используется, только если Elascticsearch находится на том же хосте, что и Filebeat; иначе надо указать другие хосты. |
| kibana_host | `"http://{{ ansible_facts['default_ipv4']['address'] }}:5601"` | Хост, на котором установлена Kibana. Значение по умолчанию используется, только если Kibana находится на том же хосте, что и Filebeat; иначе надо указать другой хост. |

Example Playbook
----------------

    - hosts: all
      roles:
         - filebeat-role

License
-------

MIT
