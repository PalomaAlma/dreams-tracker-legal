# Politique de confidentialité — Dreams Tracker

*Dernière mise à jour : 26 octobre 2026.*

## En bref

- **Sans compte, rien ne quitte votre téléphone.** Ni analytique, ni publicité,
  ni traceur tiers.
- **Avec un compte Google**, vos données sont envoyées à notre hébergeur
  (Supabase, en France) pour que vous les retrouviez sur un autre appareil ou
  sur le web. Vos fichiers vont dans **votre propre Google Drive**.
- **Deux fonctions facultatives envoient du texte à un tiers**, seulement si
  vous les utilisez : les suggestions par IA (Google, désactivées par défaut) et
  « Signaler ou suggérer » (GitHub).
- Vous pouvez tout exporter et supprimer votre compte depuis les réglages.

## Ce que l'application enregistre sur votre téléphone

Tout ce que vous y écrivez, et rien d'autre :

- vos projets, leurs étapes, leurs domaines et leurs dates ;
- vos routines, vos rituels, et les cases que vous cochez ;
- votre journal, votre humeur du jour, vos lectures, vos recettes, vos listes
  de courses (articles, quantités, prix estimés), vos transactions et objectifs
  d'épargne ;
- vos événements de calendrier créés dans l'application, et ceux que vous
  importez d'un calendrier du téléphone dans un projet (titre, jours, heures,
  couleur et description) ;
- vos photos, vidéos, mémos vocaux et documents ajoutés à un projet ;
- votre profil, s'il est renseigné : prénom, date de naissance, situation,
  disponibilité, domaines de cœur, moment préféré, votre semaine type (nuit,
  travail, engagements) et les autres réponses du formulaire ;
- vos réglages : thème, rappels, calendriers à synchroniser.

Ces données sont dans une base locale, dans l'espace privé de l'application :
aucune autre application n'y accède. Si vous posez un widget sur l'écran
d'accueil, l'application y écrit un extrait (titres de vos tâches, routines,
étapes, rituels, événements et projets de la semaine, leurs heures, votre
humeur, une idée du jour) : il est lisible par quiconque voit votre écran
d'accueil.

## Si vous vous connectez

La connexion se fait avec Google. L'application ne lit que **votre identifiant
de compte et votre adresse e-mail**. Elle ne demande ni vos contacts ni l'accès
au reste de votre Drive. Pour ouvrir votre session, elle transmet pourtant à
Supabase le jeton d'identité de Google, qui peut contenir votre nom et l'adresse
de votre photo de profil : Supabase peut les conserver. Ni l'application ni
notre serveur ne les lisent ni ne les affichent.

Ce qui part, et où :

| Quoi | Où | Quand |
|---|---|---|
| Vos fiches (tout ce qui est listé plus haut, sauf ce qui est dit dans « Ce qui ne part pas ») | Supabase, en France (Paris, `eu-west-3`) | dès que vous êtes connecté |
| Une copie de votre agenda | Supabase | connecté, accès au calendrier accordé |
| Photos, vidéos, sons, documents | votre Google Drive | connecté |
| Des éléments de vos projets, pour des idées | Google (Gemini), via notre serveur | suggestions activées, à chaque demande |
| Un signalement | GitHub, dépôt privé | quand vous appuyez sur « Envoyer » |

Comme tout service en ligne, Supabase, Google et GitHub voient l'adresse IP de
la connexion.

**Vos fiches.** Elles sont cloisonnées par compte : une règle de sécurité au
niveau de chaque ligne fait qu'un compte ne peut lire ou écrire que les siennes.

**Votre agenda.** Pour que la version web affiche vos calendriers, le téléphone
recopie, à l'ouverture de l'application (et à son retour au premier plan, au
plus toutes les 15 minutes), les événements des calendriers que vous avez
choisis dans les réglages, de 90 jours en arrière à 365 jours devant : titre,
jours et heures, nom et couleur du calendrier. Ni la description, ni le lieu, ni
les invités. Seuls les calendriers rattachés à un compte (Google, Exchange…)
sont recopiés, pas les calendriers locaux du téléphone. Désélectionner ou couper
un calendrier ne supprime rien de cette copie : elle reste chez notre hébergeur
jusqu'à la suppression de votre compte.

**Ce qui ne part pas.** Vos réglages ; l'extrait des widgets ; les fichiers
(ils vont dans votre Drive, pas chez nous) ; la copie d'un événement importé
dans un projet (ni sa description ni son lien avec le projet ne sont envoyés).
Mais l'événement lui-même est envoyé, comme n'importe quel événement de
l'agenda, si son calendrier est un calendrier de compte que vous avez choisi.

**Vos fichiers** vont dans un dossier caché de **votre propre Google Drive**,
réservé à l'application. Ils comptent dans votre stockage, pas dans le nôtre ;
ils n'apparaissent pas dans votre liste de fichiers ; aucune autre application
ne peut les lire ; et nous n'y avons pas accès.

**Se déconnecter** arrête la synchronisation. Sur le téléphone, vos données
restent sur l'appareil. Dans un navigateur, elles en sont effacées (elles se
retrouvent à la reconnexion), pour qu'une autre personne qui se connecte ensuite
sur le même ordinateur ne les reçoive pas dans son compte.

### Les suggestions par IA

Elles sont **désactivées par défaut** et demandent un compte. Une fois activées
(Réglages → « Suggestions par IA »), quand vous demandez des idées,
l'application envoie à notre serveur, qui le transmet au modèle Gemini de
Google :

- pour un projet : son titre, son domaine, sa spécialité, sa description
  (coupée à 600 caractères), le nombre de jours avant son échéance et depuis sa
  dernière activité, les outils qu'il utilise et les titres de ses tâches,
  routines et entrées d'outils ; et, seulement pour des idées d'achats, les
  titres des articles de sa liste de courses (jamais leur quantité, leur prix
  ni ce qui est coché) ;
- pour des idées de nouveaux projets : les titres, domaines et spécialités de
  vos projets en cours et les titres de quelques-unes de leurs entrées, sans
  leur description ;
- dans les deux cas, un portrait calculé sur l'appareil : répartition par
  domaine, outils utilisés ou non, heures où vous cochez, rythme, part de jours
  actifs, horizon de votre projet le plus lointain, nombre de projets à l'arrêt,
  réponses fermées du profil (tranche d'âge, situation, disponibilité, domaines
  de cœur, moment préféré, style de motivation, ambition, frein principal) et
  durées dérivées de votre semaine type (heures de travail par semaine, heures
  libres par jour, moments libres), **jamais les plages horaires elles-mêmes** ;
- les titres des idées déjà proposées, écrits par le modèle.

**Jamais** : votre date de naissance, votre prénom, votre journal, votre
humeur, vos montants, vos médias, les projets accomplis, votre adresse e-mail,
votre identifiant de compte.

**Sur l'offre gratuite que nous utilisons, Google peut conserver ces données et
les faire relire par des personnes pour améliorer ses produits.** N'écrivez
dans vos titres et descriptions rien que vous ne voudriez pas voir lu. Nous ne
pouvons pas effacer ce que Google a déjà reçu.

Notre serveur compte vos demandes du jour, pour les limiter, et ne conserve pas
votre demande. Ses journaux techniques notent les erreurs ; si le modèle répond
sans aucune idée exploitable, ils peuvent contenir sa réponse, qui peut
reprendre des termes de votre demande. Désactiver les suggestions dans les
réglages arrête tout envoi.

### Signaler un problème ou suggérer une idée

Depuis le bouton « + », « Signaler ou suggérer » envoie, si vous êtes connecté :
le genre du message (problème ou idée), votre texte, l'adresse interne de
l'écran où vous étiez (par exemple `/goal/…`, qui contient l'identifiant
technique d'un projet, pas son titre), la version de l'application, le système
(Android ou web), l'identifiant technique de votre compte (pas votre e-mail) et,
si vous la laissez cochée, **une capture de l'écran**, que vous voyez avant
l'envoi et pouvez retirer. Elle peut montrer n'importe quel contenu de votre
carnet.

Le message devient un ticket dans un dépôt **privé** de **GitHub** (notre
serveur refuse d'écrire si le dépôt n'est pas privé), lu par le développeur.
Rien n'est envoyé avant votre appui sur « Envoyer ». Dix envois par jour et par
compte au plus.

### Sauvegarde Android

L'application désactive la sauvegarde automatique d'Android
(`allowBackup="false"`) : ni la base, ni les médias, ni la session ne sont
copiés vers votre compte Google par ce mécanisme, ni transférés vers un nouveau
téléphone. Pour retrouver vos données ailleurs, connectez-vous avec un compte ou
utilisez l'export.

## Les autorisations demandées, et pourquoi

| Autorisation | À quoi elle sert |
|---|---|
| Calendrier (`READ_CALENDAR`, `WRITE_CALENDAR`) | Afficher vos rendez-vous à côté de vos routines et écrire un événement quand vous en créez un. Connecté, les événements des calendriers choisis sont aussi recopiés chez notre hébergeur (voir « Votre agenda »). |
| Microphone (`RECORD_AUDIO`) | Enregistrer un mémo vocal, au moment où vous le demandez. |
| Photos, vidéos, sons (`READ_MEDIA_IMAGES`, `READ_MEDIA_VIDEO`, `READ_MEDIA_AUDIO`) | Déclarées par la bibliothèque qui ouvre vos fichiers dans une autre application. Joindre un fichier à un projet passe par le sélecteur du système. |
| Notifications (`POST_NOTIFICATIONS`, `POST_PROMOTED_NOTIFICATIONS`, `VIBRATE`) | Poser vos rappels et la notice d'une séance en cours, calculés sur l'appareil ; aucun serveur n'en envoie. La notice d'une séance (titre de l'étape ou du pomodoro) s'affiche en entier sur l'écran de verrouillage ; pour les rappels, c'est le réglage de votre téléphone qui décide. |
| Démarrage, veille, service (`RECEIVE_BOOT_COMPLETED`, `WAKE_LOCK`, `FOREGROUND_SERVICE`) | Reprogrammer vos rappels après un redémarrage et faire tenir une séance en cours. |
| Réseau (`INTERNET`, `ACCESS_NETWORK_STATE`) | Se connecter, synchroniser, suggérer, signaler : seulement si vous vous connectez ou le demandez. |
| Biométrie (`USE_BIOMETRIC`, `USE_FINGERPRINT`) | Ajoutées par une bibliothèque ; l'application ne les utilise pas. |
| Alarmes exactes (`SCHEDULE_EXACT_ALARM`) | Faire sonner à l'heure la fin d'un minuteur et vos rappels. Refusée, l'application retombe sur une alarme moins précise. |
| Notification plein écran (`USE_FULL_SCREEN_INTENT`) | Ouvrir le minuteur à la fin d'une séance, comme une alarme. Sur Android 14 et plus, elle s'accorde dans les réglages du système. |
| Affichage par-dessus d'autres applications (`SYSTEM_ALERT_WINDOW`) | Poser la bulle optionnelle du pomodoro, seulement si vous l'activez ; rien n'est lu de ce qui se trouve dessous. |
| Google Drive (`drive.appdata`) | Sauvegarder vos fichiers dans votre propre Drive. Demandée à la connexion, refusable : les fiches se synchronisent quand même. |

## Combien de temps

Tant que vous les gardez. Quand vous supprimez quelque chose, la ligne est
d'abord marquée supprimée (c'est ce qui permet à vos autres appareils d'apprendre
la suppression), puis **effacée pour de bon au bout de 90 jours sur l'appareil
et de 180 jours sur le serveur**.

Les signalements restent dans le dépôt privé jusqu'à ce que le sujet soit
traité. Ils ne sont pas supprimés avec votre compte : écrivez-nous.

## Vos droits

- **Exporter.** Réglages → « Exporter mes données » produit un fichier JSON de
  toutes les données de cet appareil, hors éléments supprimés, médias et
  réglages. Les médias sont déjà des fichiers, sur votre téléphone et dans votre
  Drive.
- **Supprimer.** Réglages → « Supprimer mon compte » efface le compte et toutes
  vos lignes chez l'hébergeur, ainsi que vos compteurs d'envois du jour. Sur le
  téléphone, vos données restent sur l'appareil (désinstallez l'application pour
  les enlever) ; dans un navigateur, elles sont effacées. **Ne sont pas
  supprimés :** vos fichiers dans votre Drive (Drive → Paramètres → Gérer les
  applications → Dreams Tracker → Supprimer les données cachées), vos
  signalements (écrivez-nous) et ce que Google a reçu pour les suggestions.
- **Nous écrire.** paloma.alma.6@gmail.com.

## Ce que nous ne faisons pas

Pas de publicité, d'analytique, de mesure d'audience, de revente, de profilage
ni de suivi entre applications. Vos données ne vont qu'aux services nommés sur
cette page, chacun pour la fonction décrite : Supabase (synchronisation),
Google (connexion, votre Drive, et Gemini pour les suggestions si vous les
activez, avec la réserve dite plus haut) et GitHub (vos signalements). Le
développeur ne lit que les signalements que vous lui envoyez, jamais le reste de
votre carnet.

## Enfants

L'application n'est pas destinée aux enfants de moins de 13 ans et ne leur
demande rien.

## Modifications

Cette page est versionnée dans un dépôt public, qui garde l'historique de ses
changements. Un changement de fond sera annoncé dans l'application avant de
prendre effet.
