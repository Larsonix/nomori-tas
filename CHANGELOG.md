# Changelog

*English below each French line.*

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
