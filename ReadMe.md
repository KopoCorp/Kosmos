# Kosmos

Kosmos est une plateforme de provisionnement d'infrastructure développée par **Kopo**. Elle permet de créer et gérer des environnements isolés à la demande : serveurs de jeu, environnements de test ou d'entraînement en cybersécurité (red team / blue team), ou environnements applicatifs éphémères.

---

## Dépôts de l'écosystème

| Dépôt | Rôle |
|---|---|
| [Kosmos-Front](https://github.com/KopoCorp/Kosmos-Front) | Interface web et agent desktop |
| [Kosmos-API](https://github.com/KopoCorp/Kosmos-API) | Backend, authentification et logique métier |
| [Kopo-Infra](https://github.com/KopoCorp/Kopo-Infra) | Automatisation de l'infrastructure |

---

## Architecture

<img width="621" height="544" alt="image" src="https://github.com/user-attachments/assets/33867e60-cdd5-47ba-8b12-dde53bd9f6f1" />

**Kosmos-Front** est l'interface web que l'utilisateur utilise depuis son navigateur. Elle communique avec **Kosmos-API** pour toutes les opérations de gestion, et avec l'**agent desktop** pour les actions qui nécessitent un accès local à la machine (mods, VPN).

**Kosmos-API** centralise la logique métier, l'authentification et la persistance des données.

**Kopo-Infra** est la couche d'infrastructure. Il reçoit les demandes de Kosmos-API et provisionne les environnements correspondants. Ce dépôt fait partie de l'infrastructure **Kopo** au sens large et n'est pas exclusif à Kosmos.

---

## [Kosmos-Front](https://github.com/KopoCorp/Kosmos-Front)

<img width="1907" height="935" alt="image" src="https://github.com/user-attachments/assets/4467c607-d09a-4309-8162-7f77104b37a2" />

Interface web et agent desktop de la plateforme.

- **Interface web** — tableau de bord, gestion des serveurs et environnements, installation de mods, gestion du VPN et des paramètres utilisateur.
- **Agent desktop** — application locale (Windows, Linux, macOS) qui exécute les opérations nécessitant un accès à la machine de l'utilisateur. Il communique avec l'interface web via WebSocket Secure.

---

## [Kosmos-API](https://github.com/KopoCorp/Kosmos-API)

Backend de la plateforme. Il gère l'authentification, les données et orchestre les demandes vers la couche d'infrastructure.

- Authentification par token JWT et clés API
- Gestion des serveurs, des packs de mods et des utilisateurs

---

## [Kopo-Infra](https://github.com/KopoCorp/Kopo-Infra)

Couche d'automatisation de l'infrastructure. Elle reçoit les demandes de provisionnement et crée ou supprime les environnements correspondants.

- Création et suppression d'environnements isolés à la demande
- Secrets gérés via TPM2
- Déploiements CI/CD des services Kopo

---

## Technologies

| Composant | Technologies |
|---|---|
| Interface web | PHP, JavaScript |
| Agent desktop | Rust, Tauri, WireGuard |
| API backend | Python, FastAPI, MariaDB |
| Infrastructure | Python, Nginx |

---

## Licence

Propriétaire — Kopo® 2026
