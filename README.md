# SAE5.02
Sujet : Déploiement Automatisé de Serveurs DNS et DHCP pour une entreprise en pleine croissance.
 
Objectif
L'objectif est de mettre en place une solution automatisée pour gérer les services DNS et DHCP d'une entreprise en pleine croissance. Cette solution doit centraliser la gestion des adresses IP et de la résolution des noms, tout en garantissant l’évolutivité et la fiabilité des services grâce à l'automatisation.
Architecture et Outils
Infrastructure Réseau

    Serveurs DNS et DHCP : Chaque sous-réseau de l'entreprise (par exemple, Administration et Production) aura ses propres serveurs DNS et DHCP.

Conteneurs et Virtualisation

    VM Linux : Une machine virtuelle héberge les services DNS et DHCP dans des conteneurs Docker pour assurer une isolation et une portabilité.
    Conteneurs Docker :
        Serveurs DNS et DHCP : Pour chaque réseau (Administration, Production), un serveur DNS et un serveur DHCP sont déployés.
        Conteneurs de test : Des conteneurs supplémentaires permettent de simuler des clients dans chaque réseau afin de tester les services DNS et DHCP.
    Docker Compose : Permet de gérer et déployer facilement tous ces conteneurs sur les VMs.

Automatisation avec Ansible

    Ansible : Cet outil est utilisé pour automatiser le déploiement des services, leur configuration, et la vérification de leur bon fonctionnement.
    Playbooks
    Installation de Docker et Docker Compose sur la VM.
    Déploiement des conteneurs DNS et DHCP.
    Configuration des serveurs DNS (zones, cache, ACLs).
    Configuration des serveurs DHCP (plages IP, passerelles, serveurs DNS secondaires, temps de bail).
    Vérification de la résolution DNS et de l'attribution des adresses IP via DHCP avec des conteneurs de test.
    Extension du réseau avec l'ajout de nouveaux sous-réseaux et la mise à jour des configurations DNS et DHCP.
    Chaque playbook est conçu pour automatiser une étape clé du déploiement et de la gestion des services DNS et DHCP.


