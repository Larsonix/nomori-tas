# Nomori TAS

Un outil de TAS pour la démo de **Nomori** (Steam) : un mod pour le jeu, et **Nomori Studio**, l'éditeur de TAS.
Le même fichier donne la même partie, image par image.

*English version [below](#english).*

> Un jeu modifié est interdit dans les runs de tournoi. Cet outil sert à s'entraîner, à chercher et à s'amuser.
> Installez-le sur une **copie** du jeu, jamais sur le dossier que Steam lance.

## Ce qu'il fait

- **Rejoue un fichier à l'identique** : mêmes entrées, même partie, à chaque fois.
- **Pause, image suivante, image précédente**, accéléré, ralenti. Maintenir la touche fait défiler.
- **Savestates automatiques**, un par image : revenir en arrière est immédiat.
- **Image par image avec vos touches et votre souris** : vous tenez vos touches, vous bougez la souris, un clic molette joue l'image.
- **Enregistrement en direct** : vous jouez, à vitesse normale ou au ralenti, et vos entrées deviennent le fichier.
- **Visée exacte** : `Aim, yaw, pitch` place la caméra sur un angle précis, comme un coup de souris parfait.
- **Hitboxes et laser** : les formes de collision que le personnage touche, et une ligne depuis sa tête.
- **LiveSplit** suit le TAS tout seul : ouvrez LiveSplit, c'est tout.
- **Recherche** *(expérimentale)* : le jeu cherche des entrées plus rapides sur une partie de votre run.

## Ce qu'il faut

- Windows 10 ou 11, 64 bits.
- La démo de Nomori sur Steam (testé avec le build 26402932).
- Internet au premier lancement : le chargeur de mods télécharge une fois ce dont il a besoin.

## Installation

1. **Téléchargez** `Nomori-TAS.zip` dans la [dernière version](../../releases/latest) et décompressez-le.
2. **Copiez le dossier du jeu.** Dans Steam : clic droit sur Nomori Demo > Gérer > Parcourir les fichiers locaux.
   Copiez ce dossier entier ailleurs, par exemple `Documents\Nomori TAS`.
3. Ouvrez le dossier **`1 - copy into the game folder`** du kit. Copiez **tout son contenu** dans votre copie,
   à côté de `Nomori Demo.exe`.
4. Lancez **`Nomori Demo.exe`** depuis votre copie. Le premier lancement est plus long (environ une minute) :
   le chargeur de mods prépare le jeu une seule fois. Une fenêtre 1600×900 s'ouvre.
5. Lancez **`2 - Nomori Studio\CelesteStudio.WPF.exe`** et ouvrez `template.tas` (File > Open).
   Studio se connecte au jeu tout seul.
6. Dans Studio, placez le curseur sur une ligne d'entrée (une ligne qui commence par un nombre) et appuyez sur **F1**.

Pour mettre à jour : refaites l'étape 3 avec le nouveau kit et remplacez les fichiers.

Réglages par défaut de la copie : volume général 10 %, qualité basse, champ de vision au maximum, passage des
dialogues au clic droit. Vous pouvez les changer dans le menu du jeu. Deux choses à savoir : le VSync reste coupé (c'est
l'outil qui règle la vitesse du jeu), et un fichier fait avec un autre champ de vision peut se rejouer différemment
(la portée des interactions change).

## Les touches

Elles marchent dans Studio et dans la fenêtre du jeu, sauf indication.

| Touche | Effet |
|---|---|
| F1 | Nouvelle partie depuis « New Game ». Pendant un TAS : l'arrête (vous reprenez la main) ; cette image devient le départ pour placer des points avec Maj+F11 et F11 |
| F2 | Nouvelle partie, toujours |
| F3 | Pause / reprise |
| F4 | Une image en avant. Maintenu : défile |
| F5 | Une image en arrière. Maintenu : défile |
| F6 (maintenu) | Accéléré |
| F7 (maintenu) | Ralenti |
| F8 / F9 | Mémoriser cette image / l'oublier |
| F10 | Avance jusqu'au prochain `#commentaire` |
| F11 | Recherche (voir plus bas). Maj+F11 : point de passage. Ctrl+F11 : efface les points |
| F12 | Enregistrement en direct, marche / arrêt |
| ² (touche à gauche du 1) | Image par image avec vos touches. Fenêtre du jeu seulement |
| Clic molette | En image par image : joue cette image avec les touches tenues |
| Molette | Pendant un enregistrement : la vitesse (100 / 50 / 25 / 10 / 5 %) |
| H, Maj+H | Hitboxes ; Maj+H change ce qui est montré. Fenêtre du jeu seulement |
| L | Laser depuis la tête du personnage. Fenêtre du jeu seulement |

À la fin du fichier, le TAS se met en pause sur sa dernière image. **F3** vous rend le jeu.

Tout tient sur une page dans le kit : ouvrez `aide-memoire.html` dans votre navigateur.

## Le fichier

```
  30                  # 30 images sans rien (60 images ≈ 1 seconde)
  20,J                # 20 images en tenant Saut
   1,J                # un appui d'une image
  60,M,0              # avancer (M = stick gauche, angle en degrés : 0 devant, 90 droite)
  60,M,90,0.5         # aller à droite, stick à moitié
  30,M,0,C,90         # avancer en tournant la caméra à droite (C = stick droit)
Aim, 90, -20          # la ligne suivante commence en visant exactement yaw 90, pitch -20
  30,M,0
***                   # avance rapide jusqu'ici, puis pause
```

Boutons : `J` saut · `B` retour (tenu 1 s : reset) · `I` interagir · `G` attraper · `Q` portail rouge ·
`E` portail vert · `Z` remonter le temps · `R` avancer le temps · `S` menu · `K` marqueur.

- Un bouton présent sur deux lignes de suite est **un seul appui tenu**. Pour appuyer deux fois, relâchez entre les deux.
- Avancer suit la caméra : `M,0` va là où la caméra regarde.
- Le panneau d'info de Studio donne la position, la vitesse, et le yaw / pitch à recopier dans `Aim`.

## Image par image avec vos touches (²)

1. Mettez le TAS en pause sur une image, cliquez dans la fenêtre du jeu, appuyez sur **²**.
2. Tenez vos touches habituelles et bougez la souris : la caméra tourne, le temps reste figé.
3. **Clic molette** : l'image est écrite dans le fichier et jouée. Choisissez la suivante.
4. **²** à nouveau pour sortir.

Les images jouées par-dessus des images existantes les remplacent. Le reste du fichier ne bouge pas.

## Enregistrement en direct (F12)

1. **F12** à n'importe quel moment. Le jeu s'arrête sur cette image et attend.
2. Cliquez dans la fenêtre du jeu, puis appuyez sur une touche du jeu : l'horloge démarre.
3. Jouez. Chaque image devient une ligne du fichier.
4. **Molette** : la vitesse. **F5** : une demi-seconde en arrière. **Maj+F5** : une image en arrière.
   **F3** : arrête l'horloge.
5. **F12** : fin de l'enregistrement.

Rien n'est perdu : une copie de votre fichier est gardée dans `backups` à chaque départ, et chaque prise dans `takes`.

## Recherche (F11) — expérimentale

Elle part de vos entrées et essaie de petits changements pour arriver plus tôt. Deux façons de lui donner une partie
de votre run :

- **Par points** : **F1** à l'image de départ ; marchez ; **Maj+F11** aux points de passage ; **F11** à l'arrivée.
- **Par lignes** : sélectionnez des lignes dans Studio, puis **F11** (Studio au premier plan).

**F11** ou **F1** l'arrête. Le meilleur résultat est rejoué proprement avant d'être écrit, et votre fichier est
sauvegardé dans `backups` avant toute écriture. Dans ce kit, la recherche tourne dans la fenêtre du jeu : elle est
lente, et elle gagne surtout sur des parties courtes.

## LiveSplit

Ouvrez LiveSplit, avant ou après le jeu. Choisissez **Compare Against > Game Time**. Le chrono démarre et coupe
comme dans une vraie run.

## En cas de problème

- **Le jeu s'ouvre sans le mod** : vérifiez que `winhttp.dll` et le dossier `BepInEx` sont bien à côté de
  `Nomori Demo.exe`.
- **Studio ne se connecte pas** : lancez le jeu d'abord, depuis votre copie, par double-clic.
- **Les touches F ne font rien dans Studio** : le curseur doit être sur une ligne d'entrée, pas sur un `#commentaire`.

## Crédits

Fait par **Larsonix**. Portage Linux à venir par **SepiaRovilhar**.

Nomori Studio est Celeste Studio, adapté à Nomori. Le mod est chargé par BepInEx.
Les licences de ces projets sont dans [LICENSES.md](LICENSES.md).

Nomori est un jeu d'Enchanted Works. Ce projet n'est pas affilié au studio.

---

<a name="english"></a>

# Nomori TAS (English)

A TAS tool for the **Nomori** demo (Steam): a mod for the game, and **Nomori Studio**, the TAS editor.
The same file gives the same run, frame for frame.

> A modded game is banned in tournament runs. This tool is for practice, research and fun.
> Install it on a **copy** of the game, never on the folder Steam starts.

## What it does

- **Plays a file back exactly**: same inputs, same run, every time.
- **Pause, frame forward, frame back**, fast-forward, slow motion. Holding the key repeats.
- **Automatic savestates**, one per frame: stepping back is instant.
- **Frame by frame with your own keys and mouse**: hold your keys, move the mouse, a wheel click plays the frame.
- **Live recording**: you play, at real speed or slowed down, and your inputs become the file.
- **Exact aim**: `Aim, yaw, pitch` puts the camera on an exact angle, like a perfect mouse flick.
- **Hitboxes and laser**: the collision shapes the character touches, and a line from its head.
- **LiveSplit** follows the TAS by itself: open LiveSplit, that is all.
- **Search** *(experimental)*: the game looks for faster inputs on a part of your run.

## Requirements

- Windows 10 or 11, 64-bit.
- The Nomori demo on Steam (tested with build 26402932).
- Internet on the first start: the mod loader downloads what it needs once.

## Install

1. **Download** `Nomori-TAS.zip` from the [latest release](../../releases/latest) and unzip it.
2. **Copy the game folder.** In Steam: right click Nomori Demo > Manage > Browse local files.
   Copy that whole folder somewhere else, for example `Documents\Nomori TAS`.
3. Open the kit's folder **`1 - copy into the game folder`**. Copy **everything inside it** into your copy,
   next to `Nomori Demo.exe`.
4. Start **`Nomori Demo.exe`** from your copy. The first start takes longer (about a minute):
   the mod loader prepares the game once. A 1600×900 window opens.
5. Start **`2 - Nomori Studio\CelesteStudio.WPF.exe`** and open `template.tas` (File > Open).
   Studio connects to the game by itself.
6. In Studio, put the text cursor on an input line (a line starting with a number) and press **F1**.

To update: do step 3 again with the new kit and replace the files.

Default settings of the copy: master volume 10 %, low quality, field of view at its maximum, dialogue skip on the
right mouse button. You can change them in the game's menu. Two things to know: VSync stays off (the tool sets the
game's speed), and a file made with another field of view can replay differently (the reach of interactions changes).

## Keys

They work in Studio and in the game window, unless said otherwise.

| Key | Does |
|---|---|
| F1 | New run from "New Game". While a TAS plays: stops it (you get the game back); that frame becomes the start for placing points with Shift+F11 and F11 |
| F2 | New run, always |
| F3 | Pause / resume |
| F4 | One frame forward. Held: repeats |
| F5 | One frame back. Held: repeats |
| F6 (hold) | Fast-forward |
| F7 (hold) | Slow motion |
| F8 / F9 | Remember this frame / forget it |
| F10 | Fast-forward to the next `#comment` |
| F11 | Search (see below). Shift+F11: a checkpoint. Ctrl+F11: clears them |
| F12 | Live recording on / off |
| ² (the key left of 1) | Frame by frame with your own keys. Game window only |
| Wheel click | In frame by frame: plays this frame with the keys held |
| Wheel | While recording: the speed (100 / 50 / 25 / 10 / 5 %) |
| H, Shift+H | Hitboxes; Shift+H changes what is shown. Game window only |
| L | Laser from the character's head. Game window only |

At the end of the file the TAS pauses on its last frame. **F3** gives you the game back.

Everything fits on one page in the kit: open `cheatsheet.html` in your browser.

## The file

```
  30                  # 30 frames, nothing pressed (60 frames ≈ 1 second)
  20,J                # 20 frames holding Jump
   1,J                # a one-frame tap
  60,M,0              # walk forward (M = left stick, angle in degrees: 0 forward, 90 right)
  60,M,90,0.5         # walk right, half stick
  30,M,0,C,90         # walk forward while turning the camera right (C = right stick)
Aim, 90, -20          # the next line starts aiming exactly at yaw 90, pitch -20
  30,M,0
***                   # fast-forward to here, then pause
```

Buttons: `J` jump · `B` back (held 1 s: reset) · `I` interact · `G` grab · `Q` red portal ·
`E` green portal · `Z` rewind time · `R` forward time · `S` menu · `K` marker.

- A button on two lines in a row is **one press, held**. To press twice, release it in between.
- Moving follows the camera: `M,0` goes where the camera looks.
- Studio's info panel shows the position, the speed, and the yaw / pitch to copy into `Aim`.

## Frame by frame with your own keys (²)

1. Pause the TAS on a frame, click the game window, press **²**.
2. Hold your usual keys and move the mouse: the camera turns, time stays frozen.
3. **Wheel click**: the frame is written into the file and played. Choose the next one.
4. **²** again to leave.

Frames played over existing ones replace them. The rest of the file stays as it was.

## Live recording (F12)

1. **F12** at any moment. The game stops on that frame and waits.
2. Click the game window, then press a game key: the clock starts.
3. Play. Each frame becomes a line of the file.
4. **Wheel**: the speed. **F5**: half a second back. **Shift+F5**: one frame back. **F3**: stops the clock.
5. **F12**: ends the recording.

Nothing is lost: a copy of your file is kept in `backups` at every start, and every take in `takes`.

## Search (F11) — experimental

It starts from your inputs and tries small changes to arrive sooner. Two ways to give it a part of your run:

- **By points**: **F1** on the starting frame; walk; **Shift+F11** at checkpoints; **F11** at the end.
- **By lines**: select lines in Studio, then **F11** (Studio in front).

**F11** or **F1** stops it. The best result is replayed cleanly before it is written, and your file is saved
in `backups` before any write. In this kit the search runs inside the game window: it is slow, and it gains
mostly on short parts.

## LiveSplit

Open LiveSplit, before or after the game. Set **Compare Against > Game Time**. The timer starts and splits
as in a real run.

## Troubleshooting

- **The game opens without the mod**: check that `winhttp.dll` and the `BepInEx` folder sit next to
  `Nomori Demo.exe`.
- **Studio does not connect**: start the game first, from your copy, by double-click.
- **The F keys do nothing in Studio**: the cursor must be on an input line, not on a `#comment`.

## Credits

Made by **Larsonix**. Linux port to come by **SepiaRovilhar**.

Nomori Studio is Celeste Studio, re-targeted to Nomori. The mod is loaded by BepInEx.
The licences of those projects are in [LICENSES.md](LICENSES.md).

Nomori is a game by Enchanted Works. This project is not affiliated with the studio.
