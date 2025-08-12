# Site IA 0€ — GitHub Pages + GitHub Actions + TinyLlama

- **Gratuit** : hébergement GitHub Pages + génération via GitHub Actions (public repo)
- **Automatique** : un article/jour
- **Sans WordPress**, **sans API payante** : modèle open-source TinyLlama

## Mise en place (Mac, 10 minutes)

### 1) Crée un dépôt GitHub public
- Nouveau repo : `energie-portable`
- Ajoute un secret **AMZN_TAG** (ex: `monid-21`) et **AMZN_ASINS** (ex: `B09D8GKRWQ:Jackery 1000,B0B3DP4W6J:EcoFlow Delta 2`)
  - Repo → Settings → Secrets and variables → Actions → New repository secret

### 2) Envoie ces fichiers dans ton repo
- Télécharge ce kit ZIP, dézippe
- `git init && git add . && git commit -m "init"`
- `git branch -M main`
- `git remote add origin https://github.com/<toi>/energie-portable.git`
- `git push -u origin main`

### 3) Active GitHub Pages
- Repo → Settings → Pages → Build and deployment → Source: **GitHub Actions**

### 4) Laisse tourner
- Le workflow `generate-and-publish` se lance chaque jour à 06:00 UTC
- Il génère un article dans `_posts/`, commit et pousse → GitHub Pages republie

### Personnaliser
- Modifie `topics.csv` (un sujet par ligne)
- Modifie le thème via `_config.yml` (theme: minima par défaut)
- Ajoute ton texte dans `mentions.md`

### Test manuel (facultatif)
Sur ton Mac (si tu veux tester localement — non obligatoire) :
```bash
# installer python et dépendances si besoin
python3 -m venv .venv && source .venv/bin/activate
pip install -r requirements.txt
python generator.py
```

## Notes
- Les modèles open-source sont moins puissants que ChatGPT mais **gratuits**.
- Le runner GitHub dispose d’assez de minutes pour un repo public.
- Respecte les règles d’affiliation (page Mentions, rel=sponsored).
