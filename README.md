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
