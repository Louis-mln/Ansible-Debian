# Guide d'utilisation du Playbook Ansible

## Prérequis

Avant d'utiliser le playbook, assurez-vous que vous avez Ansible installé sur votre machine. Si ce n'est pas le cas, veuillez consulter la documentation officielle d'Ansible pour les instructions d'installation : https://docs.ansible.com/ansible/latest/index.html.

- apt install sudo
- apt install ansible
- apt install sshpass

## Configuration du fichier hosts

1. Ouvrez le fichier `hosts` dans le répertoire d'Ansible.
2. Entrez le nom de la machine sur laquelle vous souhaitez exécuter.
3. Spécifiez l'utilisateur à utiliser et le mot de passe si nécessaire (il est recommandé d'utiliser des clés SSH au lieu des mots de passe pour des raisons de sécurité).

Exemple :
	lmu-d12 ansible_ssh_user=root ansible_ssh_pass=azerty

# Paramétrage du Playbook default "lx_preprare_vm"

1. Ouvrez le playbook (lx_preprare_vm).
2. Adaptez les paramètres selon les besoins :

- change_machine_id: (vrai par défaut) défini si l'ID de la machine doit être changé.
- change_hostname: (vrai par défaut) défini si le nom d'hôte doit être changé.
- backup: (faux par défaut) défini si un backup doit être effectué.
- shinken: (faux par défaut) activez si vous souhaitez installer Shinken.
- resize_disk: (faux par défaut) défini si le disque doit être redimensionné.
- allow_forwarding: (faux par défaut) défini si le forwarding est autorisé.
- ssh_config: configuration spécifique pour SSH (port, root, etc.).

3. Adaptez les rôles que vous souhaitez installer dans la section roles.

# Exécution du Playbook

Une fois que tout est configuré, vous pouvez lancer le playbook en utilisant la commande suivante :

ansible-playbook -i hosts nom_du_playbook.yml
