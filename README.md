# EnR Moniteur

Appli Android (réservée au créateur) qui affiche en direct les problèmes survenus dans EnR Connect.

## Mise en route
1. **Firebase** (même projet que EnR Connect) > Paramètres du projet > Tes applications > **Ajouter une appli Android** :
   - nom du package : `com.enrmoniteur.app`
   - empreinte SHA-1 : `D7:A4:96:6C:AC:1F:B1:75:9D:0C:49:A3:B7:7C:BF:41:5B:8E:DA:81` (la même clé que EnR Connect)
   - télécharge à nouveau `google-services.json` (il contient maintenant les deux applis).
2. **GitHub** : crée un dépôt `EnR-Moniteur`, envoies-y tout le contenu de ce dossier (branche `main`). Puis Settings > **Pages** > Source : **GitHub Actions**.
3. Dépôt > Settings > Secrets and variables > Actions > **New repository secret** : `GOOGLE_SERVICES_JSON` = tout le contenu du fichier téléchargé.
4. Onglet **Actions** > « Construire l'APK » > Run workflow. Au bout de quelques minutes, l'APK est dans **Releases**.
5. Installe l'APK, connecte-toi avec ton compte **créateur** (celui du document dans la collection `createurs`).

N'oublie pas de publier le `firestore.rules` fourni avec EnR Connect (Firestore > Règles > Publier).

## Mises à jour automatiques
L'appli affiche le site `https://rahim025.github.io/EnR-Moniteur/` (adresse dans `capacitor.config.json` : change `rahim025` si ton compte GitHub est différent).
Chaque modification du dossier `www/` republie le site et l'appli se recharge toute seule à la prochaine ouverture. L'APK n'est reconstruit que pour les changements natifs (icône, config, signature).
