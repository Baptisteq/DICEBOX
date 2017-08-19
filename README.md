# DICEBOX
pure data repo. Contient les différentes versions du patch DICEBOX (main+abstracation+sample) 

# INTRO 
le patch Dicebox permet de lire 8 fichiers audio simultanément en y appliquant différent traitement simple (niveau, panoramique, EQ...) chaque traitement et leurs paramètres peuvent être configurés aléatoirement. Il est possible d'enregistrer en sortie le résultat du mix des 8 voies mais aussi d'enregistrer post-traitement chaque voie isolée. 

# PURE DATA
l'application nécessite que le logiciel PURE DATA (0.47.1) soit installé sur l'ordinateur. 
le logiciel est téléchargeable sur ce lien: https://puredata.info/downloads/pure-data

# INSTRUCTIONS
1. Installer PURE DATA 0.47.1 https://puredata.info/downloads/pure-data
2. Télécharger et extraire le dossier DICEBOX et effectuer une copie du dossier (pour récuperer une version si vous cassez tout)
3. Lancer le patch DICEBOX.1.0.pd avec PURE DATA 0.47.1 
4. afficher le log (deux stacks overflow se battent en duel il faut que je trouve la source WIP) activer le DSP (si c'est la première fois que vous lancez pure data il va falloir surement configurer le périhérique de lecture.)
5. les insructions sont indiqués sur le patch:
  
  1 - Name of the file to load: l'application lit des fichiers audios. Il cherche un nom dans le dossier SAMPLE. pour cela il faut placer un maximum de 32 fichiers mono 16bits PCM 48k ou 44.1k. et nommer ces fichiers selon la nomenclature "NOM_DU_FICHIER_"n, avec n la valeur de 1 à 32 (pas de zéro). le nom du fichier doit être identique et ne doit pas comporter d'espace. Il faut passer en mode édition pour pouvoir éditer le contenu du message pour cela le raccourci est Ctrl+E.
 
 2 - Generic name for the recorded audio. L'application enregistre puis genère automatiquement un fichier avec une certaine nomenclature "NOM_DU_FICHIER_ENREGISTRE"_ISO1_T1.wav pour l'enregistrement d'une voie isolée (1ère prise). ou "NOM_DU_FICHIER_ENREGISTRE"_MIX_T1.wav pour l'enregistrement du mix
  
  3 - Absolute Path: pour créer les fichiers directement dans le dossier RECORDED, il faut copier l'adresse absolu du dossier RECORDED (sous win7 cela prend la forme c:/users/.../.../DICEBOX.1.0/RECORDED/) c'est important que le dossier recorded ne se trouve pas dans le chemin d'accès d'un dossier comportant des espaces.
  
  4 - Specify sample Rate: spécifier le taux d'echantillonnage par défaut 48kHz (dans le futur 88.2k 96k...)
  
  5 - number of voice: c'est pas au point (par défaut 8)
  
  6 - Random loader: appuyer sur le bouton pour charger aléatoirement sur les 32 fichiers, 8 fichiers différents
  
  7 - play: joue 
  
  8 - Record armed. Appuyer sur le toggle pour que le prochain play active aussi l'enregistrement. L'enregistrement coupe automatiquement une seconde après qu'il n'y ai plus de signal... normalement :)
  
  # à propos du dossier RECORDED:
  l'application génère à chaque enregistrement 9 fichiers: 8 stéréos Isolés et un stéreo Mix (ISO1, ISO2, ... ,ISO8, MIX) pour rendre plus clair le dossier il est utile de classer les fichiers par date de création.
  
  dans le dossier SAMPLE il y a déjà plusieurs banque. revenir à l'étape 1, et taper au choix EAU,EOLIENNE ou TOLE (les majusucles sont pas nécessaires j'aime quand c'est gros)  

# CREDITS

RJ_lib https://github.com/rjdj/rjlib (abstractions e_pan et s_playtable)
Johannes Kreidler Johannes Kreidler (abstraction: granular)
http://www.pdpatchrepo.info/hurleur/randomize-urn-vanilla.pd (urn-vanilla)
Audio: les fichiers EOLIENNE ont été enregistré et publié sur la sonothèque de sounddesigners.org par FRIZOO (https://www.sounddesigners.org/sonotheque/download/22-vent/7617-eoliennes-st.html)

