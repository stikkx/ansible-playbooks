# ansible

ansible `playbooks`, `inventory` und `roles`  für die Konfiguration der PCs und Server und die Installation eines Docker Infrastruktur Servers.

## Infrastruktur-Server

### requirements installieren

`ansible-galaxy install -r rq.infra-server.yml`

### ansible Playbook starten

`ansible-playbook -i hosts pb.infra-server.yml`
