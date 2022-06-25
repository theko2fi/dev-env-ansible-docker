# dev-env-ansible-docker
Credit: Xavki

# Windows Subsytem for Linux version 2 (WSL 2)

## Systemd
Pour faire fonctionner ce script sous Windows for Subsystem Linux (WSL 2), il vous faut installer docker d'abord (évident). Et puisque les conteneurs déployés par ce script utilisent systemd, qui n'est pas disponible par défaut dans WSL 2. Vous devrez d'abord exécuter les commandes suivantes dans WSL 2:
```bash
sudo mkdir /sys/fs/cgroup/systemd
sudo mount -t cgroup -o none,name=systemd cgroup /sys/fs/cgroup/systemd
```

## Static DNS
Puisque j'exécute ce script dans Windows for Subsystem Linux (WSL 2), il arrive que mes conteneurs n'arrivent pas à accéder à Internet à cause d'un problème de DNS. J'ai donc été une fonction specifyNameServer pour spécifier le serveur DNS à utiliser lors de la création ou du démarrage de mes conteneurs.
