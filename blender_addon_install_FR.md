<p align="center">
  <img src="/imgs/addon_install_guide.png">
</p>

# Comment installer des addons Blender - guide complet

[English version here](https://github.com/Pullusb/How_to_install_Blender_addons/blob/master/README.md)

#### Tout d'abord, cher utilisateur, sache qu'il y a deux "modèles" d'addons:

Fichier simple :  
Juste un fichier python style "*mon_addon.py*"

![single file addon](/imgs/single_file_addon.png)

Multi fichiers :  
Un dossier "*mon_addon*" qui contient toujours (et au moins) un "*\_\_init\_\_.py*".  
Les addons multifichiers sont toujours zippé.

![multi-file addon](/imgs/multi-file_addon.png)


## Comment installer ?

### La méthode facile

Ouvrer les préfèrences > onglet addons > cliquez sur "install..." et aller chercher le fichier "*.py"* ou "*.zip"*.

![basic install](/imgs/basic_install.png)

Puis il s'affiche seul dans la liste, et vous avez juste a cocher "enable".

![activate addon](/imgs/activate_addon.png)


Là c'est déjà fini. Vous pouvez vous contenter de cette méthode et vous arrêter ici (Sauf si l'addon utilise des modules, ce qui est plutôt rare)  
Mais la suite s'avèrera utile pour bien comprendre le fonctionnement et organiser vos addons de manière plus efficace.

Toujours là ? Parfait !

## Installation manuelle

Une fois un addon placé manuellement dans les dossiers sources il faut cliquer sur refresh s'il n'apparaît pas dans la liste.

Analysons les différents endroits où se trouvent les addons (et modules python).  
Il y a en a 3:

### - Release

Placé dans le dossier d'installation.

ex windows : `C:\Program Files\Blender Foundation\Blender\2.80\scripts\addons\`

![release](/imgs/release.png)

Les addons "release" sont ceux qui sont livré par défaut avec blender.  
Ils se trouvent dans le dossier d'installation blender, sous son numéro de version.  
Les fichiers sont locaux a cette version seulement, vous pouvez placer vos addons ici sans problème, mais le dossier "user" que nous verrons ensuite est dédié a cet usage.

> notez que les sortie intermediaire (release candidate) arrive avec un lot d'addons supplémentaire appelé "contrib". S'il sont intégré, ils seront stocké dans le dossier "addons_contrib" a coté du dossier "addons". Les adddons "contrib" sont ceux qui n'ont pas encore pu être intégré par défaut pour diverse raison mais qui sont généralement très intéressants.


### - Users

Placé dans les dossier perso de l'utilisateur.

ex windows : `C:/Users/username/AppData/Roaming/Blender Foundation/Blender/2.80/scripts/addons`  
ex linux : `~/user/config/blender/2.80/scripts/addons`

![user scripts and config](/imgs/user_scripts_and_config.png)

C'est à cet endroit où va votre fichier quand vous utilisez la méthode automatique !  
Voici ce qui se passe lorsque vous cliquez sur "Install...":
- copie du "*.py*: dans les "user addons" (ou dézip à cet endroit si c'est une archive)
- rafraîchissement de la liste des addons (bouton refresh) pour qu'il apparaisse.
- nom de l'addon dans le champ de recherche pour l'afficher seul.

> note : Si vous n'avez jamais installé d'addons via l'installeur de blender, les dossier "scripts/addons" ne seront probablement pas présent dans le dossier de version. Il suffit de les créer (idem pour le dossier "script/modules")

Pourquoi ici et pas dans les dossier d'installations de blender ?  
Et bien si vous installez a nouveau Blender ou même que vous utilisez une version portable.
L'emplacement restera le même et vos addons seront chargé sans avoir à les copier ailleurs.

Bonus : C'est pour les même raisons que les préférences utilisateur sont aussi sotckées a cet emplacement, à côté du dossier "script" vous trouverez "config" qui contient préférences (userpref.blend), fichier de démarrage (startup.blend), l'historique d'ouverture, etc.


### - Externes

Dans le dossier de votre choix (optionnel, pas défini par défaut).

Vous définissez ce chemin dans `Preferences > File Paths > Scripts`.  

![external scripts](/imgs/external_scripts.png)

Comme mentionné [dans la documentation officielle](https://docs.blender.org/manual/en/latest/editors/preferences/file_paths.html#data), le dossier ciblé doit contenir la même structure que les deux autres emplacement.  
Donc dans ce dossier (qui ne doit pas nécessairement s'appeler "scripts") créez un sous-dossier "addons" (et le dossier "modules" si besoin)

Cet emplacement est très intéressant car il vous permet de cibler un répertoire sur un serveur local par exemple.  
Donc toutes les machines sur un même réseau local peuvent charger les addons depuis le même dossier ce qui est bien pratique pour les mises à jour.

---

C'est bon, vous savez maintenant où les addons sont stocké et pourquoi. Vous pouvez les organisez à votre manière. <span>&#128077;</span>


> Dernière note : Dans mon addon [DevTools](https://github.com/Pullusb/devTools) vous avez des boutons pour ouvrir directement ces emplacements dans votre explorateur depuis la sidebar du text-editor.


Blendez bien.

Samuel (PullUSB)

![logo SB](/imgs/logo_sb_80px.png)
