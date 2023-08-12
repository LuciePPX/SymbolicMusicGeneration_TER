# SymbolicMusic_LSTM

## FolderSource

- ClassicalMusic MIDI *(folder)*

    Dossier de 19 compositeurs de musique classique contenant chacun 1 (pour Balakir) à 48 (pour Chopin) morceaux de musique au format midi (.mid)

- MusicGenerated *(folder)*

    Contient 4 morceaux de musique au format Waveform Audio (.wav) :
        - **Corpus_Snippet.wav** qui est utilisé pour jouer un morceaux de musique *cellule 15*
        - **Melody_Generated_1.wav Melody_Generated_2.wav** qui sont les 2 musiques générées après entrainement du modèle. *cellule*

- CodeSource_FirstModel.ipynb *(file)*

    Fichier source au format notebook écrit en Python3 
    Tout le code a été adapté pour que son lancement soit éffectuer directement dans le dossier **SymbolicMusic_LSTM** 
    
    + Ajout des modifications pour utiliser MuseScore3 **( [à télécharger grâce à ce lien :](https://ftp.osuosl.org/pub/musescore-nightlies/windows/3x/stable/) )
    la ligne de code dans la cellule des importations sera à adapter : 
    environment.set('musescoreDirectPNGPath' r"C:\Program Files\MuseScore 3\bin\MuseScore3.exe")** à la place de LilyPond *(application non fonctionnelle aujourd'hui)*

    L'exécution de se fichier lance un entrainement de 200 epochs sur les musiques de Chopin *(dossier de la base de donnée fourni qui le plus de musique)*
    Cette execution est tel que nous l'avons trouvé et a pris sur nos machines **20 heures**
    Nous avons sauvegarder cette entrainement dans **"./Myfolder/dossier_de_sauvegarde"**, ce dossier nous a permis de faire un transfert learning sur notre propre base de donnée.

## MyFolder

- Dossier_de_sauvegarde *(folder)*  
     
    Dossier permettant de faire un transfert learning sur le fichier **ModelLSTM_myBDD.ipynb**.

- generation de partition.ipynb *(file)*

    Fichier Notebook codé à l'aide de chatGPT et python3 afin de faire des tests de remplacement de code des parties utilisant Lilypond dans le code source.


- ModelLSTM_allBDD.ipynb *(file)*

    Notebook codé en Python3 adapté du fichier **CodeSource_FirstModel.ipynb** qui entraine sur 200 epochs son modèle sur toute la base de donnée **ClassicalMusic_MIDI**.
    
    BUT RECHERCHE : amélioré la generation de musique.

    ABOUTISSEMENT : Temps estimé à 200h, nos machines personnelles n'étant pas assez performantes, lancement du fichier abandonné.

- ModelLSTM_myBDD.ipynb *(file)*

    Fichier utilisant de **dossier de sauvegarde** pour faire le machine learning sur notre propre base de donnée:

    #téléchargement de la base de donnée

    filepath = "../myBDDD_trompet/"
    #Liste de tous les fichiers midi 
    all_midis= []
    for f in os.listdir(filepath):
        if f.endswith(".mid"):
            tr = filepath+f
            midi = converter.parse(tr)
            all_midis.append(midi)


        ou 

    #téléchargement de la base de donnée
    
    filepath = "../myBDDD_trompet/"
        #Liste de tous les fichiers midi 
        all_midis= []
        for f in os.listdir(filepath):
            if f.endswith(".mid"):
                tr = filepath+f
                midi = converter.parse(tr)
                all_midis.append(midi)

    RESULTAT : ...



