# Streamlit Keep-Alive

Outil d'automatisation basé sur **GitHub Actions** et **Playwright** pour empêcher les applications déployées sur **Streamlit Community Cloud** de basculer en mode veille (*sleep mode*).

### Pourquoi ce projet ?
Les moniteurs HTTP classiques (comme UptimeRobot) reçoivent un code `200 OK` même lorsqu'une application Streamlit est endormie (page statique *« Zzzz… »*). Ce projet lance un navigateur headless pour charger réellement la page et cliquer automatiquement sur le bouton **« Yes, get this app back up ! »** si nécessaire.

### Fonctionnalités
- **Déclenchement automatique** : exécution planifiée via cron (toutes les 8 heures).
- **Déclenchement manuel** : bouton `Run workflow` disponible à tout moment dans l'onglet *Actions*.
- **Multi-applications** : surveillance d'une liste illimitée d'URLs Streamlit en une seule exécution.
- **Résilience** : gestion des timeouts, détection automatique des boutons de réveil et logs détaillés.

### Installation & Utilisation
1. Clonez ce dépôt ou forkez-le.
2. Ouvrez `.github/workflows/keep_alive.yml`.
3. Mettez à jour la variable `STREAMLIT_URLS` avec les URLs de vos applications :
   ```python
   STREAMLIT_URLS = [
       "[https://mon-application-1.streamlit.app](https://mon-application-1.streamlit.app)",
       "[https://mon-application-2.streamlit.app](https://mon-application-2.streamlit.app)",
   ]

## English 

Automation tool powered by **GitHub Actions** and **Playwright** designed to prevent applications deployed on **Streamlit Community Cloud** from going into hibernation (*sleep mode*).

### Why this project?
Standard HTTP monitoring tools (such as UptimeRobot) receive a `200 OK` status code even when a Streamlit application is asleep, because Streamlit displays a static HTML landing page (*“Zzzz…”*). This project launches a headless browser to fully load the page and automatically click the **“Yes, get this app back up!”** wake button whenever required.

### Features
- **Automated triggers**: scheduled execution using a GitHub cron schedule (every 8 hours).
- **Manual trigger**: `Run workflow` button available on demand within the *Actions* tab.
- **Multi-app support**: monitors an unlimited list of Streamlit URLs in a single run.
- **Resilience**: timeout handling, automatic wake button detection, and structured console logs.

### Setup & Usage
1. Clone or fork this repository.
2. Open `.github/workflows/keep_alive.yml`.
3. Update the `STREAMLIT_URLS` list with your target application URLs:
   ```python
   STREAMLIT_URLS = [
       "[https://my-app-1.streamlit.app](https://my-app-1.streamlit.app)",
       "[https://my-app-2.streamlit.app](https://my-app-2.streamlit.app)",
   ]
