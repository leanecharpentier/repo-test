# Comprendre Git Flow
Git Flow est un workflow qui se base sur le fonctionnement par branche de Git.

Voici le principe de base : 
* Votre projet sera basé sur 2 branches principales ```master``` et ```develop```, impossible à modifier.
*  Pour intéragir avec ces branches, il est possible de créer, via Git Flow, des branches ```feature```, ```release``` et ```hotfix```. Nous verrons par la suite à quoi correspond chacune de ces branches.

## Pré-requis & Installation
Pour utiliser Git Flow, il faudra évidemment installer Git sur votre machine. Vous pouvez l'installer en cliquant [ici](https://git-scm.com/)

Une fois Git installé, il faudra procéder à l'installation de Git Flow :

### OSX - Homebrew
```
brew install git-flow
```

### OSX - Macports
```
ports install git-flow
```

### Linux
```
apt-get install git-flow
```

### Windows (Cygwin)
```
wget -q -O - --no-check-certificate https://github.com/nvie/gitflow/raw/develop/contrib/gitflow-installer.sh | bash
```

## Les principales fonctionnalités

Une fois Git Flow installé, vous devrez l'initialisé dans votre répertoire Git :
```
cd my/project
git flow init
```

### Feature
La branche ```feature``` est généralement basé sur votre branche ```develop```. Elles sont utilisées pour développer les fonctionnalités de votre projet.

Pour créer une branche ```feature```, vous devez faire la commande suivante :
```
git flow feature start [NOM_DE_LA_FEATURE]
```

Lorsque vous avez terminé de développer la fonctionnalité, il faut merger votre fonctionnalité à la branche ```develop```.
```
git flow feature finish [NOM_DE_LA_FEATURE]
```

### Release
Lorsque vous avez développé plusieurs fonctionnalités et que vous souhaitez les ajouter à votre branche master, vous devez créer une branche```release```. Elle est donc basé sur votre branche ```develop```.

Pour créer une branche ```release```, vous devez faire la commande suivante :
```
git flow release start [NOM_DE_LA_RELEASE]
```

Lorsque vous souhaitez merger votre release sur la branche ```master```.
```
git flow release finish [NOM_DE_LA_RELEASE]
```

### Hotfix
La branche ```hotfix``` est basé sur votre branche ```master``` et permet de résoudre des bugs de production rapidement.

Pour créer une branche ```hotfix```, vous devez faire la commande suivante :
```
git flow hotfix start [NOM_DE_LA_HOTFIX]
```

Lorsque vous souhaitez est merger sur la branche ```master``` et ```develop```.
```
git flow hotfix finish [NOM_DE_LA_HOTFIX]
```

