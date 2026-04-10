# Green and Coop — données météo (dbt)

Ce dépôt regroupe le projet **dbt** et le **docker-compose** pour Postgres local.

## Contenu

| Élément | Rôle |
|--------|------|
| `greenandcoop_project/` | Projet dbt (modèles, sources, packages) |
| `docker-compose.yml` | Postgres 15 pour le développement local |

Les dossiers **`dbt-env/`** (environnement Python) et **`logs/`** ne sont pas versionnés : à recréer sur chaque machine (voir ci‑dessous).

## Prérequis

- Python 3.11+ (recommandé)
- Docker (pour Postgres via compose)

## Mise en route

```bash
python3 -m venv dbt-env
source dbt-env/bin/activate   # Windows : dbt-env\Scripts\activate
pip install -r requirements.txt
cd greenandcoop_project
dbt deps
```

Configurer un profil dbt (`profiles.yml`) avec la base Postgres (ex. variables du `docker-compose.yml`). Ne pas committer de mots de passe.

Lancer la base :

```bash
docker compose up -d
```

## Licence / usage

Usage interne ou selon la politique du projet.
