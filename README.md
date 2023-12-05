# BetterDiscord-Animated-Status_Fixed

* [Installation](#installation)
* [Utilisation](#utilisation)
  * [Délai d'attente (Timeout)](#délai-dattente)
  * [L'Éditeur](#léditeur)
  * [Emojis](#emojis)
    * [Emoji standard](#emoji-standard)
    * [Emoji Nitro](#emoji-nitro)
  * [Exemples](#exemples)

## Installation
Installez en utilisant le très pratique [https://github.com/BetterDiscord/Installer] \
Téléchargez [Animated_Status_Fixed_plugin.js](/Animated_Status_Fixed_plugin.js?raw=true) dans le répertoire suivant \
Mac: `~/Library/Preferences/BetterDiscord`\
Windows: `%appdata%\BetterDiscord\plugins`\
Linux: `~/.config/BetterDiscord/plugins`

## Utilisation
Ouvrez Discord, allez dans Paramètres\>Plugins, activez AnimatedStatus et cliquez sur Paramètres.\
Saisissez les informations requises dans les champs de saisie et cliquez sur le bouton `Enregistrer` (save).
Cliquez sur `Terminé` (Done) sans enregistrer pour annuler vos paramètres.


### Délai d'attente
La valeur spécifie la durée de chaque étape d'animation en millisecondes.
Exemple: Avec un délai de 2000, l'animation suivante prendrait 4 secondes pour se terminer, car 2 images clés durent chacune 2 secondes.
Pour éviter que le serveur Discord ne soit inondé de demandes, le délai d'attente minimum autorisé est codé en dur pour être de 2.9 secondes. \
Logiquement, le délai d'attente de l'animation devrait être d'au moins `2900`. Idéalement, il devrait être d'environ `10000` millisecondes (10 secondes) pour que l'animation paraisse fluide sur les autres clients. \
Dans l'application mobile, le statut n'est pas mis à jour de manière cohérente, c'est-à-dire que la liste des membres du serveur est mise à jour en fonction des actions des utilisateurs dans l'application. Ne soyez pas surpris si l'animation ne semble pas fluide ou saute des images. \
^ Selon [@pintoso](https://github.com/pintoso)

### L'Éditeur
Chaque cellule ajoutée avec le bouton `+` ajoute une nouvelle étape à l'animation du statut. \
Cliquez sur le bouton `-` pour supprimer la dernière étape. \
Une cellule vide réinitialisera temporairement votre statut. Cela a été ajouté suite à une demande, mais cela peut changer à l'avenir.

Dans la dernière version, la décision a été prise de supprimer l'éditeur brut du plugin. C'était simplement une interface textuelle instable vers le fichier de configuration JSON. \
**Vous pouvez toujours utiliser le mode BRUT (RAW)**, en cliquant sur `Ouvrir le dossier des plugins` dans les paramètres et en éditant `AnimatedStatus.config.json`. Faites-le à vos risques et périls, vous pourriez casser des choses.

### Emojis
#### Emoji standard
Utilisez un sélecteur d'emoji (Windows: <kbd>Win</kbd>+<kbd>.</kbd>). \
Alternativement, utilisez [une table Unicode](https://unicode.org/emoji/charts/full-emoji-list.html) et copiez l'emoji que vous souhaitez avoir comme statut. \
Le champ `emoji_name` **ne doit pas contenir d'espaces**. Sinon, le serveur Discord ignorera silencieusement votre demande de statut.
En raison d'incertitudes sur les noms d'emoji Nitro, le plugin ne supprime actuellement pas automatiquement les espaces.

#### Emoji Nitro
- Ouvrez un chat Discord, tapez `\`. \
 
- Sélectionnez l'emoji que vous souhaitez inclure dans votre statut à l'aide du sélecteur d'emoji. \
 
- Remarquez que le message a changé en `<:nom_de_lemoji:identifiant_emoji>`. Les valeurs à l'intérieur des crochets (nom_de_lemoji et identifiant_emoji) sont les valeurs requises pour le statut. \
 
- Modifiez les paramètres en conséquence \


### Exemples
Certaines captures d'écran sont accélérées, afin que le ReadMe paraisse plus attrayant.

#### Horloge
- **Résultat:** \
  <img src="Screenshots/JS_Clock.gif">
- **Champ Emoji:** \
  <code> eval ['🕛','🕐','🕑','🕒','🕓','🕔','🕕','🕖','🕗','🕘','🕙','🕚'][((new Date()).getHours()%12)]; </code>

#### Horloge Et Texte
- **Résultat:** \
  <img src="Screenshots/JS_ClockText.png">
- **Champ Emoji:** \
  <code> eval ['🕛','🕐','🕑','🕒','🕓','🕔','🕕','🕖','🕗','🕘','🕙','🕚'][((new Date()).getHours()%12)]; </code>
- **Champ Texte:** \
  <code> eval let fmt=t=>(t<10?'0':'')+t;let d=new Date();\`${fmt(d.getHours())}:${fmt(d.getMinutes())}:${fmt(d.getSeconds())}\`; </code>
