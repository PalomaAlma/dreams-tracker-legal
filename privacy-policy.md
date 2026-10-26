# Politique de confidentialité — Dreams Tracker

*Dernière mise à jour : 24 octobre 2026.*

> **À compléter avant publication** — deux valeurs ne peuvent pas être devinées
> depuis le dépôt et sont marquées `⟨…⟩` plus bas : l'adresse de contact du
> responsable de traitement, et la région d'hébergement du projet Supabase
> (visible dans Project Settings → General). Le Play Store refuse une politique
> sans moyen de contact.
>
> La section « Les suggestions » décrit le **palier gratuit** de l'API Gemini.
> Si la facturation est activée un jour, remplacer la phrase sur Google par :
> « Google traite ces données pour notre compte et ne les utilise pas pour
> entraîner ou améliorer ses modèles. », et repasser la ligne correspondante
> de `play-data-safety.md` en « non partagée ».

## En un paragraphe

Dreams Tracker est un carnet d'objectifs personnels. **Sans compte, rien ne
quitte votre téléphone.** L'application fonctionne entièrement hors ligne, et
c'est son mode par défaut : il n'y a ni analytique, ni publicité, ni traceur
tiers, ni collecte de quoi que ce soit à notre profit. Si vous vous connectez
avec un compte Google, et seulement dans ce cas, vos données sont recopiées
ailleurs pour que vous les retrouviez sur un autre appareil — les fiches chez
notre hébergeur, les fichiers dans **votre propre Google Drive**.

## Ce que l'application enregistre

Tout ce que vous y écrivez, et rien d'autre :

- vos projets, leurs étapes, leurs domaines et leurs dates ;
- vos routines, vos rituels, et les cases que vous cochez ;
- votre journal, votre humeur du jour, vos lectures, vos recettes, vos
  listes de courses (articles, quantités, prix estimés), vos transactions et
  objectifs d'épargne ;
- vos événements de calendrier créés dans l'application ;
- vos photos, vidéos, mémos vocaux et documents ajoutés à un projet ;
- votre profil, s'il est renseigné : prénom, date de naissance, situation,
  disponibilité, domaines de cœur, moment préféré de la journée et les
  autres réponses du formulaire de profil ;
- vos réglages : thème, rappels, calendriers à synchroniser.

Ces données sont dans une base de données locale, dans l'espace privé de
l'application sur votre appareil. Aucune autre application n'y accède.

Si vous posez un widget sur l'écran d'accueil de votre téléphone, l'application
y écrit un extrait de vos données (par exemple les titres de vos tâches, de vos
routines et de vos rituels du jour, votre humeur, une idée du jour) dans ses
préférences privées : il est donc lisible par quiconque voit votre écran
d'accueil. Rien n'en sort de l'appareil.

## Si vous vous connectez

La connexion se fait avec Google. L'application ne lit et n'utilise que
**votre identifiant de compte et votre adresse e-mail** (elle ne demande ni vos
contacts ni l'accès au reste de votre Drive : seulement, plus bas, son dossier
caché). En revanche, pour ouvrir votre session, elle
transmet à Supabase le jeton d'identité que Google fournit, et ce jeton peut
contenir votre nom et l'adresse de votre photo de profil Google : Supabase peut
les conserver dans la fiche de votre compte. Ni l'application ni notre serveur
ne les lisent ni ne les affichent.

**Les fiches** (tout ce qui est listé ci-dessus, sauf les fichiers et vos
réglages, qui restent sur l'appareil ; les événements que vous avez importés
d'un calendrier du téléphone dans un projet ne sont pas envoyés non plus) sont
recopiées chez **Supabase**, notre hébergeur de base de données, en ⟨région
d'hébergement à renseigner⟩. Elles y sont cloisonnées par compte : une règle de
sécurité au niveau de chaque ligne fait qu'un compte ne peut lire ou écrire que
les siennes.

**Votre agenda.** Pour que la version web affiche vos calendriers, le
téléphone recopie, à l'ouverture de l'application (et à son retour au premier
plan, au plus toutes les 15 minutes), les événements des calendriers que vous avez
choisis dans les réglages, si vous avez accordé l'accès au calendrier : leur
titre, leurs jours et heures, et le nom et la couleur de leur calendrier, de 90
jours en arrière à 365 jours devant. Ni la description, ni le lieu, ni les
invités. Seuls les calendriers rattachés à un compte (Google, Exchange…) sont
recopiés : un calendrier local au téléphone ne l'est pas. Désélectionner ou
couper un calendrier dans les réglages ne supprime rien de cette copie : les
événements déjà recopiés restent chez notre hébergeur jusqu'à la suppression de
votre compte.

**Les fichiers** (photos, vidéos, sons, documents) vont dans **votre propre
Google Drive**, dans un dossier caché réservé à l'application
(`appDataFolder`). Ils ne comptent pas dans notre stockage mais dans le vôtre ;
ils n'apparaissent pas dans votre liste de fichiers Drive ; aucune autre
application ne peut les lire ; et **nous n'y avons pas accès** — nous ne
possédons pas ce dossier, vous si.

Se déconnecter arrête la synchronisation. Sur le téléphone, les données
restent sur l'appareil. Dans un navigateur, elles en sont effacées — elles se
retrouvent à la reconnexion — pour qu'une autre personne qui se connecte
ensuite sur le même ordinateur ne les reçoive pas dans son compte.

**Les suggestions.** Elles sont **désactivées par défaut** et demandent un
compte. Une fois activées (Réglages → « Suggestions par IA »), quand vous
demandez des idées, l'application envoie à notre serveur, qui le transmet au
modèle Gemini de Google :

- pour un projet : son titre, son domaine, sa spécialité, sa description (coupée
  à 600 caractères), le nombre de jours avant son échéance et depuis sa dernière
  activité, les outils qu'il utilise et les titres de ses tâches, routines et
  entrées d'outils ; et, seulement quand vous demandez des idées d'achats, les
  titres des articles de sa liste de courses (jamais leur quantité, leur prix
  ni ce qui est coché), pour ne pas vous proposer ce que la liste porte déjà ;
- pour des idées de nouveaux projets : les titres, domaines et spécialités de
  vos projets en cours et les titres de quelques-unes de leurs entrées, sans
  leur description ;
- dans les deux cas, un portrait calculé sur l'appareil : répartition de vos
  projets par domaine, outils utilisés ou non, heures où vous cochez, rythme,
  part de jours actifs, horizon de votre projet le plus lointain, nombre de
  projets à l'arrêt, et les réponses fermées de votre profil (tranche d'âge,
  situation, disponibilité, domaines de cœur, moment préféré, style de
  motivation, ambition, frein principal), ainsi que des durées dérivées de
  votre semaine type (heures de travail par semaine, heures libres par jour,
  moments libres) — **jamais les plages horaires elles-mêmes** ;
- les titres des idées déjà proposées, écrits par le modèle, pour qu'il n'en
  répète pas.

Jamais votre date de naissance, votre prénom, votre journal, votre humeur, vos
montants, vos médias, ni les projets accomplis (ils sont écartés du portrait et
de l'inspiration). Ni votre adresse e-mail ni votre identifiant de compte ne
sont transmis à Google : notre serveur fait l'intermédiaire. **Sur l'offre gratuite que nous utilisons, Google peut
conserver ces données et les faire relire par des personnes pour améliorer
ses produits** : n'écrivez dans vos titres et descriptions rien que vous ne
voudriez pas voir lu. Notre serveur compte vos demandes du jour, pour limiter
leur nombre par personne, et ne conserve pas votre demande. Ses journaux
techniques notent les erreurs ; dans un cas d'échec (une réponse du modèle dont
aucune idée n'est exploitable), ils peuvent contenir la réponse du modèle, qui
peut reprendre des termes de votre demande. Les suggestions se désactivent dans
les réglages (« Suggestions par IA ») : plus rien ne part alors vers l'IA.

**Signaler un problème ou suggérer une idée.** Depuis le bouton « + »,
« Signaler ou suggérer » envoie, si vous êtes connecté : le genre du message
(problème ou idée), le texte que vous écrivez, l'adresse interne de l'écran où
vous étiez (par exemple `/goal/…`, qui contient l'identifiant technique d'un
projet, pas son titre), la version de l'application, le système (Android ou
web), l'identifiant technique de votre compte (pas votre adresse e-mail) et, si
vous la laissez cochée, **une capture de l'écran** que vous voyez avant l'envoi
et que vous pouvez retirer. Ce message devient un ticket dans un dépôt **privé**
hébergé par **GitHub** (notre serveur refuse d'écrire si le dépôt n'est pas
privé), lu par le développeur de l'application. Rien n'est envoyé sans que vous
ayez appuyé sur « Envoyer ». Le nombre d'envois est limité à dix par jour et par
compte.

**Sauvegarde Android.** L'application désactive la sauvegarde automatique
d'Android (`allowBackup="false"`) : ni la base de données, ni les médias, ni la
session ne sont copiés vers votre compte Google par ce mécanisme ni transférés
automatiquement vers un nouveau téléphone. Pour retrouver vos données ailleurs,
connectez-vous avec un compte (synchronisation décrite plus haut) ou utilisez
l'export.

## Les autorisations demandées, et pourquoi

| Autorisation | À quoi elle sert |
|---|---|
| Calendrier (`READ_CALENDAR`, `WRITE_CALENDAR`) | Afficher vos rendez-vous à côté de vos routines, et écrire un événement quand vous en créez un. Sans compte, tout se passe sur l'appareil. Connecté, les événements des calendriers que vous avez choisis sont recopiés chez notre hébergeur pour la version web (voir « Votre agenda »). |
| Microphone (`RECORD_AUDIO`) | Enregistrer un mémo vocal. Uniquement au moment où vous le demandez. |
| Photos, vidéos, sons (`READ_MEDIA_IMAGES`, `READ_MEDIA_VIDEO`, `READ_MEDIA_AUDIO`) | Déclarées par la bibliothèque qui ouvre vos fichiers dans une autre application. Joindre une photo, un clip ou un document à un projet se fait par le sélecteur du système, au moment où vous le demandez. |
| Notifications (`POST_NOTIFICATIONS`, `POST_PROMOTED_NOTIFICATIONS`, `VIBRATE`) | Poser vos rappels et la notice d'une séance en cours. Ils sont calculés et déclenchés sur l'appareil ; aucun serveur ne les envoie. La notice d'une séance en cours (titre de l'étape ou du pomodoro) s'affiche en entier sur l'écran de verrouillage ; l'affichage des rappels suit le réglage de votre téléphone. |
| Démarrage, veille, service (`RECEIVE_BOOT_COMPLETED`, `WAKE_LOCK`, `FOREGROUND_SERVICE`) | Reprogrammer vos rappels après un redémarrage du téléphone, et faire tenir une séance en cours. Aucune ne transmet de donnée. |
| Réseau (`INTERNET`, `ACCESS_NETWORK_STATE`) | Synchroniser, suggérer, signaler, se connecter — seulement si vous vous connectez ou le demandez. `ACCESS_NETWORK_STATE` est ajoutée par une bibliothèque. |
| Biométrie (`USE_BIOMETRIC`, `USE_FINGERPRINT`) | Ajoutées par une bibliothèque ; l'application ne demande aucune empreinte ni reconnaissance du visage. |
| Alarmes exactes (`SCHEDULE_EXACT_ALARM`) | Faire sonner à la seconde près la fin d'un minuteur de rituel ou d'un pomodoro, et vos rappels à l'heure choisie. Refusée, l'application retombe sur une alarme moins précise. |
| Notification plein écran (`USE_FULL_SCREEN_INTENT`) | Réveiller l'écran et ouvrir le minuteur à la fin d'une séance, comme une alarme. Sur Android 14 et plus, elle s'accorde depuis les réglages du système. |
| Affichage par-dessus d'autres applications (`SYSTEM_ALERT_WINDOW`) | Poser la bulle optionnelle du pomodoro au-dessus des autres applications. Demandée seulement si vous l'activez dans les réglages ; rien n'est lu de ce qui se trouve dessous. |
| Google Drive (`drive.appdata`) | Sauvegarder vos fichiers médias dans votre propre Drive. Demandée seulement si vous vous connectez, et refusable — les fiches se synchronisent quand même. |

## Combien de temps

Tant que vous les gardez. Quand vous supprimez quelque chose, la ligne est
d'abord marquée supprimée — c'est ce qui permet à vos autres appareils
d'apprendre la suppression au lieu de la ressusciter — puis **effacée pour de
bon au bout de 90 jours sur l'appareil et de 180 jours sur le serveur**.

Les signalements et idées envoyés restent dans le dépôt privé jusqu'à ce que
le sujet soit traité, puis peuvent être supprimés à votre demande. Ils ne sont
pas supprimés automatiquement avec votre compte : écrivez-nous pour le faire.

## Vos droits

- **Exporter.** Réglages → « Exporter mes données » produit un fichier JSON
  contenant toutes les données de cet appareil (les éléments que vous avez
  supprimés n'y figurent pas), que vous pouvez partager où vous voulez. Les
  fichiers médias n'y sont pas : ils sont déjà des fichiers, dans le stockage
  de votre téléphone et dans votre Drive. Vos réglages (thème, rappels…) n'y
  sont pas non plus.
- **Supprimer.** Réglages → « Supprimer mon compte » efface le compte et, avec
  lui, toutes vos lignes chez l'hébergeur — elles sont rattachées au compte par
  une clé qui les emporte, ainsi que vos compteurs d'envois du jour. Sur le
  téléphone, vos données restent sur l'appareil (désinstallez l'application
  pour les enlever) ; dans un navigateur, elles sont effacées du navigateur.
  **Les fichiers de votre Drive restent
  aussi les vôtres** : ils sont dans votre compte Google, pas dans le nôtre.
  Pour les retirer, Drive → Paramètres → Gérer les applications → Dreams
  Tracker → Supprimer les données cachées de l'application.
- **Nous écrire.** ⟨adresse de contact à renseigner⟩.

## Ce que nous ne faisons pas

Pas de publicité. Pas d'analytique ni de mesure d'audience. Pas de revente.
Pas de profilage. Pas de suivi entre applications. Vos données ne vont qu'aux
services nommés sur cette page, chacun pour la fonction décrite : Supabase
(synchronisation), Google (connexion, votre Drive, et Gemini pour les
suggestions si vous les activez — avec la réserve dite plus haut sur l'usage
que Google peut en faire) et GitHub (vos signalements). Le développeur
ne lit que les signalements et idées que vous lui envoyez, jamais le reste de
votre carnet.

## Enfants

L'application n'est pas destinée aux enfants de moins de 13 ans et ne leur
demande rien.

## Modifications

Cette page est versionnée dans le dépôt du projet. Un changement de fond sera
annoncé dans l'application avant de prendre effet.
