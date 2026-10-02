# Outil Formulation

Un seul fichier, `Outil Formulation.html`, remplace les deux Excel de l'équipe formulation
(`RAPPORT.FORMU.LIVE.xlsx` et `étiquette_SB_NEW.xlsx`). Rien à installer et pas d'internet : on
l'ouvre dans **Microsoft Edge** ou **Google Chrome**. Firefox l'ouvre aussi, mais il ne peut pas
enregistrer directement dans le dossier : la sauvegarde y passe par un téléchargement.

Quatre onglets, sans rechargement de page :

- **Accueil** : la date, la dernière sauvegarde, le verdict du shift et le dernier lot d'étiquettes.
- **Rapport de shift** : la synthèse en haut, la saisie en dessous, le PDF et le mail.
- **Étiquettes** : les planches Fiducial 115294 pour SB4, SB5, SB5B, SB16 et CT-P17.
- **Paramètres** : tout ce qui se règle sans toucher au code.

---

## Mise en place

Le **dossier principal** sur N: contient :

```
Outil Formulation.html   ← l'outil
sauvegarde.js            ← les données de l'équipe (créé au premier Ctrl+S)
Octobre 26/              ← un dossier par mois, avec les PDF des rapports (créé tout seul)
```

1. Copiez `Outil Formulation.html` dans ce dossier.
2. Ouvrez-le avec Edge (clic droit › Ouvrir avec › Microsoft Edge), puis épinglez un raccourci.
3. Au premier **Ctrl+S** sur un PC, Edge demande d'autoriser le dossier : choisissez le dossier
   principal, puis cliquez sur **Autoriser**. Edge peut le redemander à chaque nouvelle session ;
   c'est une sécurité du navigateur.

## Sauvegarde

- **Ctrl+S** (ou **Enregistrer**), depuis n'importe quel onglet, écrit tout dans `sauvegarde.js` :
  le rapport, les étiquettes et les paramètres.
- À l'ouverture, sur n'importe quel PC, l'outil relit `sauvegarde.js` tout seul.
- Un point orange sur Enregistrer signale ce qui n'est pas encore écrit sur N:. Tout reste aussi
  gardé dans le navigateur du PC.
- Si un collègue a enregistré entre-temps, l'outil le signale et ne remplace jamais une saisie
  non enregistrée sans demander.
- Si `sauvegarde.js` est abîmé, l'outil prévient et en garde une copie avant de le remplacer.
- Restent propres à chaque PC : la calibration de l'imprimante d'étiquettes, la taille du texte
  (Aa) et le thème clair ou sombre.

## Rapport de shift

- **Le shift se choisit tout seul** selon l'heure : Matin 6–14, Après-midi 14–22, Nuit 22–6 ;
  Week-end AM 10–22 et Week-end PM 22–10, du vendredi 22 h au dimanche 22 h. La date du rapport
  est celle du début du shift.
- **Synthèse**, calculée toute seule (personne ne la remplit) :
  - les commentaires épinglés (Critique en rouge, Attention en jaune) ;
  - « À traiter » et « Bientôt » ;
  - les échantillons au frigo ;
  - une colonne par machine avec ses lots, leur parcours, leurs holding times et leurs remarques.

  Aucun N/A n'est affiché.
- **Saisie** : une carte par machine et par lot, rangée dans l'ordre du procédé. Les étapes
  faites se replient et l'étape en cours est ouverte. W3 et poids formulé sont toujours en kg.
- **Holding times** : chacun a un nom, un départ et une fin. Il s'arrête tout seul (par exemple
  quand Connexion passe à FAIT) ou avec le bouton **✓ Fait**. Il reste ensuite affiché
  « Respecté » ou « Dépassé ».
- **Vide de ligne** : remet à N/A les champs de production du lot (sauf l'échantillon), puis
  propose **Passer au lot suivant**. Le lot suivant devient le lot en cours, et les holding times
  encore en cours le suivent. L'échantillon de l'ancien lot va dans « Échantillons à suivre ».
- **Clôturer le shift** : enregistre, crée le PDF et le range dans `<Mois AA>/Rapport formulation
  JJ-MM-AAAA <Shift>.pdf`, puis ouvre Outlook Web prérempli (destinataire du groupe formulation,
  objet = nom du PDF). Il reste à joindre le PDF : son nom exact est rappelé. Si Edge ne peut pas
  écrire, l'outil propose l'impression Edge (Imprimante : « Enregistrer au format PDF »).

## Étiquettes

- Planche **Fiducial 115294** (A4, 65 étiquettes de 38,1 × 21,2 mm), standard mesuré et validé :
  marges 10,7 / 9,75 mm, décalage Y +1 mm, échelle 100 %.
- À l'impression : papier **A4** (pas Lettre), échelle **100 %**, imprimante **copieur** (pas
  « Enregistrer au format PDF »).
- **Réinitialiser les paramètres** revient exactement au standard.
- Visa de 3 à 6 lettres, ou vide pour l'écrire à la main.

## Paramètres

Ce qui se règle :

- les holding times : durées, nom, départ, fin, seuil d'alerte, et des holding times personnalisés ;
- le parcours (étapes) par machine et par produit ;
- les produits ;
- les champs concernés par produit ;
- les couleurs des lignes ;
- le mail ;
- les modèles d'étiquettes ;
- le dossier principal.

Chaque section a son bouton **Rétablir cette section par défaut**, et chaque holding time ou
parcours modifié a un **Rétablir** individuel.

## À savoir

Cet outil sert à la communication d'équipe et à préparer les étiquettes. Il ne remplace ni le
dossier de lot ni les documents GMP officiels. Relisez toujours les étiquettes avant de les coller.
Avant de généraliser son utilisation, faites valider l'outil par QA et IT, comme tout outil
bureautique utilisé en production.
