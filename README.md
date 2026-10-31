# TP1 — Déploiement automatisé d'un Portfolio Next.js avec Ansible

## 1. Présentation du projet

Ce TP consiste à automatiser le déploiement d'une application Portfolio
développée avec Next.js à l'aide d'Ansible.

L'objectif est de préparer automatiquement un serveur Linux, installer
Node.js et PM2, récupérer le code source de l'application, construire
l'application Next.js et configurer Nginx comme reverse proxy.

## 2. Technologies utilisées

- Ubuntu Linux
- Ansible
- Node.js 22
- npm
- Next.js
- PM2
- Nginx
- Git

## 3. Architecture du projet

```text
portfolio-deploy/
│
├── ansible.cfg
├── site.yml
│
├── inventory/
│   └── hosts.ini
│
├── group_vars/
│   └── all.yml
│
└── roles/
    ├── common/
    │   └── tasks/
    │       └── main.yml
    │
    ├── nodejs/
    │   └── tasks/
    │       └── main.yml
    │
    ├── app/
    │   ├── tasks/
    │   │   └── main.yml
    │   └── handlers/
    │       └── main.yml
    │
    └── nginx/
        ├── tasks/
        │   └── main.yml
        ├── handlers/
        │   └── main.yml
        └── templates/
            └── portfolio.conf.j2
