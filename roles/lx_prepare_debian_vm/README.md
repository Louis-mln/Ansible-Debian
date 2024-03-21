lx_prepare_vm
=========

Fonctionnalités :
  - Configuration du nom d'hôte avec le nom de l'inventaire Ansible
  - Configuration du Pare-feu (SSH et backup)
  - Configuration pour la supervision Shinken
  - Ajout des clés SSH sur le compte ROOT de l'équipe Linexos sur
  - Installation d'epel-release et de différents outils
  - Mise en place de règles de sécurités et d'optimisations (Sysctl et limits)
  - Possibilité d'autoriser l'IP forwarding
  - Configure Chrony (NTP)
  - Permet d'étendre la partion sda2 (Après augmentation du disque côté hyperviseur)
  - Installation de Bacula pour les sauvegardes

Road map:
  - Installation des agents beats elk (Filebeat,auditbeat,metricbeat et packetbeat)
    - Avec configuration des modules
  - Installation de l'agent Wazuh
  - Mise en place d'NRPE (Ou agent Linexos)
  - Clé SSH poller en variables
  - Installation de NTP

Example Playbook
----------------
    ---
    - hosts: localhost
      roles:
        - lx_prepare_vm
      vars:
        change_hostname: true # Default value : true
        backup: false # Default value : false
        shinken: false # Default value : false
        resize_disk: false # Default value : false
        allow_forwarding: false # Default value : false
        ssh_config: 
          port: 22  # Default value : 22
          root: enable  # Default value : enable
          listen: # Default value : - "0.0.0.0"
            - "0.0.0.0"
        php_config:
          install: true
