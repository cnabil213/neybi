# Outil Formulation

Un seul fichier, `Outil Formulation.html`, remplace les deux Excel de l'équipe formulation
(`RAPPORT.FORMU.LIVE.xlsx` et `étiquette_SB_NEW.xlsx`). Il s'ouvre sur un **accueil** avec deux
tuiles, et des onglets en haut permettent de passer d'un module à l'autre à tout moment :

- **Rapport de shift** : état des lots sur Groninger, Inova 5 et Inova 4, export PDF et mail au groupe formulation ;
- **Étiquettes** : planches d'étiquettes pour les échantillons SB4, SB5, SB5B et SB16.

Rien à installer, pas besoin d'internet : on double-clique sur le fichier, il s'ouvre dans
**Microsoft Edge** ou **Google Chrome**.

---

## Mise en place

1. Copiez `Outil Formulation.html` dans le dossier partagé de l'équipe, par exemple
   `N:\MFG\Formulation\Outil formulation`.
2. Ouvrez-le avec Edge (clic droit → *Ouvrir avec* → *Microsoft Edge*).
3. Ajoutez un raccourci sur le bureau pour y revenir facilement.

---

## Rapport de shift

- **Saisie** : cliquez directement sur les statuts (N/A, EN COURS, FAIT…). Les couleurs sont les
  mêmes que dans l'Excel : vert = fait / prêt, jaune = en cours, rouge = à faire / en attente,
  bleu ❄ = au frigo.
- **Champs grisés** : un champ qui ne concerne pas le produit choisi s'affiche en grisé avec la
  mention « Non applicable ». Par exemple, le monitoring n'apparaît que pour SB16, CT-P17 et SB5B,
  et le check shift que pour TAKEDA.
- **Holding times** : quand vous saisissez une date de début, la limite se calcule toute seule
  (150 h Groninger ; 20 / 24 / 34 h Inova 5 ; 24 / 32 / 34 / 144 h Inova 4 ; 72 h et 24 h pour le
  lot suivant). Le bandeau du haut affiche les échéances et passe en jaune quand il reste moins de
  4 h, puis en rouge une fois la limite dépassée.
- **Alerte FRIGO** : dès qu'un échantillon est « AU FRIGO », le bandeau le signale.
- **Lot terminé → passer au suivant** : en un clic, le lot suivant passe en cours et le lot
  suivant +1 devient le lot suivant. Plus besoin de tout recopier.
- **Annuler** : le bouton Annuler (ou Ctrl+Z) revient en arrière si vous vous trompez.

### Enregistrement et passation entre shifts

- Tout s'**enregistre automatiquement** sur le PC à chaque modification (voir « ✓ Enregistré »
  en haut). En rouvrant le fichier, on retrouve le rapport tel qu'on l'a laissé.
- **Partage entre PC** (à finaliser selon le test du disque N:) : si l'équipe utilise plusieurs PC, ouvrez *⋯ → Sauvegarde & partage → Lier un fichier* et
  créez `rapport-formulation-donnees.json` **dans le dossier Teams synchronisé**. Le rapport y est
  alors écrit automatiquement, et le shift suivant, sur un autre PC, retrouve le même état en liant
  le même fichier. Si quelqu'un a enregistré une version plus récente, l'outil le signale.
  Cette fonction marche dans Edge et Chrome (pas dans Firefox).
- **Sauvegarde de secours** : *⋯ → Exporter / Importer* un fichier `.json`.

### Envoyer le rapport

1. **Exporter en PDF**. Dans la fenêtre d'impression, choisissez « Enregistrer au format PDF »
   et l'orientation Paysage. Le nom du fichier est proposé automatiquement (date + shift). Chaque
   export est aussi gardé dans l'**Historique**, qu'on peut revoir et réimprimer.
2. **Préparer le mail**. Outlook s'ouvre avec l'objet, un résumé (alertes, points à suivre) et les
   destinataires. Il ne reste qu'à **joindre le PDF**. Les adresses du groupe formulation se
   règlent une fois pour toutes dans *⋯ → Paramètres*.

---

## Étiquettes

1. **Produit & lot** : choisissez SB4, SB5, SB5B ou SB16, puis saisissez le lot. La date et le visa
   sont facultatifs : sans eux, un blanc est laissé pour écrire à la main. La date est écrite comme
   dans l'Excel, par exemple `29Sep26`.
2. **Poches** : ajoutez autant de lots de poches que nécessaire, avec leur nombre de poches et,
   si besoin, le N° client de la 1ʳᵉ poche. Il n'y a plus de limite de 8 lots ni de 52 poches, et
   il n'y a plus de page « 1 à 13 / 14 à 26 » à choisir : toutes les pages sont générées.
3. **Autres échantillons** : la liste du produit est préremplie. On peut cocher ou décocher des
   lignes, en ajouter (sans limite) et enregistrer sa propre liste par défaut.
4. **Imprimer** : l'aperçu à droite montre exactement ce qui sortira.

### Réglages d'impression

- Le gabarit par défaut reproduit **exactement la mise en page de l'Excel**. Chaque poche occupe
  une rangée de 4 étiquettes. D'autres gabarits sont proposés (65 étiquettes L7651, papier normal
  avec traits de coupe, personnalisé).
- Dans la fenêtre d'impression, **laissez les réglages par défaut** (surtout pas « Ajuster à la page »).
- La première fois, imprimez une **page de test** sur papier normal, posez-la sur une planche
  d'étiquettes à contre-jour, puis corrigez si besoin le **décalage X/Y** (en mm) ou l'**échelle** (si le décalage grandit vers le bas). Le réglage est
  mémorisé sur le PC.
- **Première ligne libre** : pour réutiliser une planche déjà entamée.
- **Poches de … à …** : pour réimprimer seulement quelques poches.

---

## Corrections par rapport aux Excel

- *Rapport* : certaines mises en forme conditionnelles pointaient vers de mauvaises cellules (le
  grisage de Pesée, Tampon et Sortie frigo sur le lot suivant, et l'indicateur FRIGO pour le lot
  suivant), si bien qu'elles ne fonctionnaient pas. C'est corrigé. La « Limite HT (150 h) »
  Groninger est maintenant calculée automatiquement.
- *Étiquettes* : pour SB16, les quantités des « autres étiquettes » étaient décalées d'une ligne à
  partir de `Step2_BB_Val (2/6)`. Par exemple, `Step2_Endo_Val` sortait en 250 mL au lieu de 3 mL.
  C'est corrigé.

## À savoir

- Ces outils servent à la communication d'équipe et à préparer les étiquettes. Ils ne remplacent
  pas le dossier de lot ni les documents GMP officiels. Relisez toujours les étiquettes avant de
  les coller. Avant de généraliser leur utilisation, vérifiez avec QA / IT s'ils doivent être
  déclarés, comme tout outil bureautique utilisé en production.
- Les données restent sur vos PC et dans votre dossier Teams. Rien n'est envoyé sur internet.
