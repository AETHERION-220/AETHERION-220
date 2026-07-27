# Salut, je suis therion 

<!-- L'image alignée à droite. Remplace le lien 'src' par l'URL de l'image de ton choix -->
<a href="#">
  <img align="right" width="320" src="URL_DE_TON_IMAGE.png" alt="Anime Character" />
</a>

Je suis un étudiant en informatique et un passionné de cybersécurité. J'aime construire des projets, de l'architecture de bases de données à l'ingénierie inverse, en passant par le développement d'écosystèmes comme Innova ou le Projet Nostos.

### 🛠️ Mes Outils & Technologies
*   **Langages :** Python, C, C++, Java, JavaScript, Assembleur, SQL
*   **Environnements & OS :** Arch Linux, Ubuntu, Docker, Environnements virtuels
*   **Domaines d'intérêt :** Cybersécurité, Pentesting, Analyse réseau, Systèmes embarqués

---

### 📊 Mes Statistiques GitHub

<!-- Widget GitHub Stats de base -->
<p align="center">
  <img src="https://github-readme-stats.vercel.app/api?username=TON_USERNAME_GITHUB&show_icons=true&theme=tokyonight" alt="GitHub Stats" />
</p>

<!-- Widget GitHub Streak (La Flamme) -->
<p align="center">
  <img src="https://streak-stats.demolab.com?user=TON_USERNAME_GITHUB&theme=tokyonight" alt="GitHub Streak" />
</p>

<!-- Widget des langages les plus utilisés -->
<p align="center">
  <img src="https://github-readme-stats.vercel.app/api/top-langs/?username=TON_USERNAME_GITHUB&layout=compact&theme=tokyonight" alt="Top Languages" />
</p>
<picture>
  <source media="(prefers-color-scheme: dark)" srcset="profile-3d-contrib/profile-night-view.svg">
  <source media="(prefers-color-scheme: light)" srcset="profile-3d-contrib/profile-view.svg">
  <img alt="GitHub 3D Contribution Calendar" src="profile-3d-contrib/profile-night-view.svg" width="100%">
</picture>
name: GitHub-Profile-3D-Contrib

on:
  schedule:
    - cron: "0 18 * * *" # Se met à jour tous les jours
  workflow_dispatch: # Permet de le lancer manuellement

jobs:
  build:
    runs-on: ubuntu-latest
    name: generate-github-profile-3d-contrib
    steps:
      - uses: actions/checkout@v3
      - uses: yoshi389111/github-profile-3d-contrib@0.7.1
        env:
          GITHUB_TOKEN: ${{ secrets.GITHUB_TOKEN }}
          USERNAME: ${{ github.repository_owner }}
      - name: Commit & Push
        run: |
          git config user.name github-actions
          git config user.email github-actions@github.com
          git add -A .
          git commit -m "Mise à jour du calendrier 3D"
          git push
