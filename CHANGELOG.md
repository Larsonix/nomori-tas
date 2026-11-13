# Changelog

*English below each French line.*

## v1.3 — 2026-11-13

Pour mettre à jour : copiez à nouveau le contenu de `1 - copy into the game folder` dans votre copie du jeu et
remplacez les fichiers. Il y a de nouveaux fichiers dans `BepInEx/patchers` et `tools/sim`. **Nomori Studio a changé :
remplacez son dossier.**
/ To update: copy the content of `1 - copy into the game folder` into your copy of the game again and replace the
files. There are new files in `BepInEx/patchers` and `tools/sim`. **Nomori Studio changed: replace its folder.**

### Recherche (F11) / Search (F11)

- **La recherche joue maintenant tous les objets, sur les six niveaux.** Slimes, saisie, fleur, portes de sortie,
  dialogues et cinématiques, rotation des portails, réapparition, ponts qui s'effondrent, pales du moulin, Kodamas,
  retour dans le temps, créatures. Elle change aussi les boutons d'objets (I, B, G, Q, E), le moment d'une prise ou d'un
  lâcher, la visée d'un lancer, les gâchettes du temps (Z, R) et la caméra pendant une saisie. Des gains confirmés par
  le vrai jeu sur chaque niveau.
  / **The search now plays every object, on all six levels.** Slimes, the grab, the flower, exit gates, talks and
  cutscenes, turning portals, the respawn, collapsing bridges, the windmill's blades, Kodamas, the time rewind,
  creatures. It also changes object buttons (I, B, G, Q, E), when you grab or let go, a throw's aim, the time triggers
  (Z, R) and the camera during a grab. Gains confirmed by the real game on every level.
- **Le strafe aérien.** En l'air, la recherche pousse de côté et saute dès l'atterrissage : elle garde et gagne de la
  vitesse (jusqu'à 9,08 m/s au strafe, plus avec un rebord). Exemple : le premier clip d'Arrival garde 10,9 m/s au lieu
  de 8,7.
  / **Air strafing.** In the air the search pushes sideways and jumps on the landing step: it keeps and gains speed (up
  to 9.08 m/s by strafing, more off an edge). Example: Arrival's first clip keeps 10.9 m/s instead of 8.7.
- **Un nouveau moteur de recherche, qui n'est plus collé à votre run.** Il explore hors de votre trajet : autres moments
  de saut, autres chemins, détours pour prendre de la vitesse. Il a une carte de chaque niveau (le temps qui reste depuis
  n'importe où, portails compris) et la liste de tous les rebords et coins qui donnent de la vitesse : en tombant dessus,
  en les touchant de côté, ou en sautant dedans (comme dans le feuillage de l'arbre avant la sortie d'Arrival). La carte
  et la liste se construisent à la première recherche sur un fichier (environ une minute, pendant que la recherche
  tourne déjà), puis sont gardées. Il en est à ses débuts : ses plus gros gains arrivent dans les prochaines versions.
  / **A new search engine, no longer stuck to your run.** It explores off your path: other jump moments, other ways,
  detours to gain speed. It has a map of each level (the time left from anywhere, portals included) and the list of
  every edge and corner that gives speed: falling onto it, touching it from the side, or jumping up into it (like into
  the leaves of the tree before Arrival's exit). The map and the list are built on the first search of a file (about a
  minute, while the search already runs), then kept. It is early: its biggest gains come in the next versions.
- **Repères `# keep`.** Une ligne `# keep` après une ligne de votre fichier oblige chaque essai à reproduire ce
  résultat (l'endroit où vous êtes posé ; `# keep speed` : votre vitesse). L'écran dit pour chaque repère l'image
  atteinte et la vôtre. Les repères restent à leur place quand un run est écrit.
  / **`# keep` marks.** A `# keep` line after a line of your file makes every try reproduce that result (where you
  stand; `# keep speed`: your speed). The screen shows, per mark, the frame reached and yours. Marks stay in place when
  a run is written.
- **Plus audacieuse quand elle bloque :** après 10 s sans gain, les changements grandissent.
  / **Bolder when stuck:** after 10 s without a gain, the changes grow.

### Retour en arrière (F5) / Stepping back (F5)

- **F5 est exact sur les six niveaux, de toutes les façons :** F5 simple, F5 maintenu, pendant un enregistrement,
  pendant la lecture, dans les emplacements. Tout revient comme à cette image : physique, créatures, animations, jambes
  du personnage, matériaux, minuteries.
  / **F5 is exact on all six levels, every way:** plain F5, held F5, while recording, while playing, in the slots.
  Everything comes back as it was on that frame: physics, creatures, animations, the character's legs, materials,
  timers.
- **F5 en image par image** : une image en arrière, vous restez en image par image (même avec un enregistrement ouvert
  et pendant un reset).
  / **F5 in frame by frame**: one frame back, you stay in frame by frame (even with a recording open and during a
  reset).
- **F5 maintenu ne va plus jamais vers l'avant.**
  / **Held F5 never goes forward any more.**
- **Un savestate coûte 2 à 4 ms au lieu de 6 à 14,** et chaque image en vitesse réelle en garde un : plus de saccades.
  / **A savestate costs 2 to 4 ms instead of 6 to 14,** and every real-speed frame keeps one: no more stutter.

### Nouveau / New

- **La molette choisit la vitesse d'enregistrement à tout moment**, avant même F12 ; la vitesse s'affiche.
  / **The wheel sets the recording speed at any moment**, even before F12; the speed is shown.
- **Une touche qui ne fait rien dit pourquoi**, dans le titre de la fenêtre du jeu, dans Studio et à l'écran.
  / **A key that does nothing says why**, in the game window's title, in Studio and on screen.
- **`Level, D2` suffit** : le code seul, le numéro ou le nom, sans souci de majuscules.
  / **`Level, D2` is enough**: the code alone, the number or the name, in any case.

### Corrigé / Fixed

- **L'image par image ne repart plus en vitesse normale.** Quand une image ne pouvait pas être rechargée, le mode se
  coupait et le fichier se jouait jusqu'au bout ; l'image est maintenant jouée en rejouant le fichier, et vous restez en
  image par image.
  / **Frame by frame no longer drops back to normal speed.** When a frame could not be reloaded, the mode switched off
  and the file played on to its end; the frame is now played by replaying the file, and you stay in frame by frame.
- **Le clic molette maintenu ne s'arrête plus après une ou deux secondes.** Nomori Studio réécrivait sa propre copie du
  fichier juste après chaque image, et effaçait la dernière.
  / **The held wheel click no longer stops after a second or two.** Nomori Studio wrote its own copy of the file back
  right after each frame, erasing the newest one.
- **La molette ne perd plus de crans** entre l'enregistrement et l'image par image.
  / **The wheel no longer loses notches** between the recording and frame by frame.
- **Molette vers le haut depuis l'image par image : l'enregistrement attend votre première touche** (il ne part plus
  tout seul).
  / **Wheel up from frame by frame: the recording waits for your first game key** (it no longer starts by itself).
- **Les icônes de boutons ne sont plus des carrés blancs** quand vous visez un portail ou un objet : ce sont les
  boutons Xbox.
  / **Button prompts are no longer white squares** when you aim at a portal or an object: they show the Xbox buttons.
- **Un crash** : revenir en arrière après une saisie puis rappuyer sur le bouton du bloc (Windmill) fermait le jeu.
  / **A crash**: stepping back after a grab, then pressing the block's button again (Windmill), closed the game.
- **La recherche ne s'arrête plus d'elle-même sur une partie très courte.**
  / **The search no longer stops by itself on a very short part.**
- **Le chrono du titre de niveau** était décalé d'une image après un retour en arrière.
  / **The level title's timer** was one frame off after a step back.
- **Recherche sur des lignes sélectionnées** : elle part du New Game, et une partie plus rapide au milieu d'un fichier
  est écrite à sa propre longueur. **Plus de lignes de 0 image** (`0,M,0`) écrites par la recherche.
  / **Search on selected lines**: it starts from New Game, and a quicker part in the middle of a file is written at its
  own length. **No more 0-frame lines** (`0,M,0`) written by the search.
- **« Rien trouvé »** n'est plus annoncé comme un échec : vos lignes sont gardées.
  / **"Nothing found"** is no longer reported as a failure: your lines are kept.

### À savoir / Good to know

- **F8 et F9 ne font plus rien** : Maj + un chiffre garde une image, le chiffre seul y revient.
  / **F8 and F9 do nothing now**: Shift + a number key keeps a frame, the number key alone goes back to it.
- Si l'image par image se comporte mal, envoyez le fichier `LabData\7777\tas_events.log` de votre dossier du jeu : il
  note chaque touche refusée et pourquoi.
  / If frame by frame misbehaves, send the file `LabData\7777\tas_events.log` from your game folder: it records every
  refused key and why.

## v1.2 — 2026-11-12

Pour mettre à jour : copiez à nouveau le contenu de `1 - copy into the game folder` dans votre copie du jeu et
remplacez les fichiers. Il y a un nouveau dossier, `tools`. Nomori Studio n'a pas changé.
/ To update: copy the content of `1 - copy into the game folder` into your copy of the game again and replace the
files. There is a new folder, `tools`. Nomori Studio did not change.

### Nouveau / New

- **Recherche rapide (F11) pour tout le monde.** La recherche tourne maintenant hors du jeu, sur tous vos cœurs : des
  milliers d'essais par seconde au lieu de quelques-uns. Chaque gain est vérifié par le vrai jeu avant d'être écrit.
  / **Fast search (F11) for everyone.** The search now runs outside the game, on all your cores: thousands of tries a
  second instead of a few. Every gain is checked by the real game before it is written.
- **Elle marche sur les six niveaux.**
  / **It works on all six levels.**

### À savoir / Good to know

- La première recherche télécharge un fichier depuis le serveur de Unity (environ 25 Mo, une seule fois). Il faut
  internet cette fois-là.
  / The first search downloads one file from Unity's server (about 25 MB, once). It needs the internet that one time.
- Une recherche démarre après environ 20 secondes : l'outil rejoue d'abord votre fichier jusqu'au départ dans une copie
  cachée du jeu.
  / A search starts after about 20 seconds: the tool first replays your file up to the start in a hidden copy of the
  game.
- La recherche rapide joue la marche, les sauts et la caméra. Sur une partie avec des objets qui bougent, ou avec
  d'autres boutons que le saut, elle peut ne rien gagner.
  / The fast search plays walking, jumping and the camera. On a part with moving objects, or with buttons other than
  jump, it may gain nothing.
- Le retour en arrière avec F5 est toujours en cours de correction.
  / Stepping back with F5 is still being fixed.

## v1.1 — 2026-11-12

Pour mettre à jour : copiez à nouveau le contenu de `1 - copy into the game folder` dans votre copie du jeu et
remplacez les fichiers. Nomori Studio n'a pas changé.
/ To update: copy the content of `1 - copy into the game folder` into your copy of the game again and replace the
files. Nomori Studio did not change.

### Nouveau / New

- **Dix emplacements de savestate.** Maj + une touche de la rangée du haut (1 à 9, 0) garde l'image ; la touche seule
  y revient. Un emplacement dont l'état ne peut plus être chargé rejoue le fichier jusqu'à cette image.
  / **Ten savestate slots.** Shift + a top-row key (1 to 9, 0) keeps the frame; the key alone goes back to it. A slot
  whose state can no longer be loaded replays the file up to that frame.
- **Une seule molette pour l'enregistrement (F12) et l'image par image (²).** Pendant un enregistrement, un cran sous
  5 % passe en image par image. En image par image, la molette vers le haut reprend l'enregistrement à 5 %.
  / **One wheel for live recording (F12) and frame by frame (²).** While recording, one notch below 5 % switches to
  frame by frame. In frame by frame, wheel up resumes the recording at 5 %.
- **Clic molette maintenu** en image par image : le jeu avance à 25 % avec vos touches et votre souris.
  / **Wheel click held** in frame by frame: the game runs at 25 % with your keys and mouse.
- **² et F12 sortent chacun des deux modes.**
  / **² and F12 each leave both modes.**

### Corrigé / Fixed

- **Image par image qui se dérègle après un moment** (caméra folle, jeu qui repart à vitesse normale, ² qui ne sort
  plus). Trois causes corrigées : un fichier modifié dans Studio pendant le mode, le mode qui restait actif quand le
  TAS s'arrêtait dessous, et l'aperçu de la caméra appliqué sur des images qui tournent.
  / **Frame by frame going wrong after a while** (camera going wild, the game back at normal speed, ² no longer
  leaving). Three causes fixed: a file edited in Studio while the mode is on, the mode staying on when the TAS stopped
  under it, and the camera preview applied on running frames.
- **Coup de caméra en revenant de l'image par image vers l'enregistrement** : la souris repartait d'un mauvais angle.
  / **Camera swing when going from frame by frame back to recording**: the mouse turned from the wrong angle.
- **Recherche (F11)** : une partie qui finit en sortant du niveau n'est plus refusée quand elle est plus rapide.
  / **Search (F11)**: a part that ends by leaving the level is no longer refused when it is quicker.

### Documentation

- Les six noms de niveau pour `Level,` et les fichiers à envoyer pour signaler un problème sont dans le README.
  / The six level names for `Level,` and the files to send when reporting a problem are in the README.

### Connu / Known

- Revenir en arrière avec F5 plusieurs fois de suite peut laisser le jeu dans un état qui ne correspond pas au
  fichier (objets qui bougent, actions en cours). F1 ou F2 remet tout d'aplomb. En cours de correction.
  / Stepping back with F5 many times in a row can leave the game in a state that does not match the file (moving
  objects, actions under way). F1 or F2 puts everything right. Being fixed.
- La recherche de ce kit tourne dans la fenêtre du jeu et reste lente. La recherche rapide n'est pas encore dans le
  kit public.
  / The search of this kit runs inside the game window and stays slow. The fast search is not in the public kit yet.

## v1.0 — 2026-11-11

Première version publique. / First public release.
