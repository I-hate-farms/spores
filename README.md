# Spores
[Spores](http://i-hate-farms.github.io/spores) is the ppa for all our applications and libraries

## How to install
```
sudo add-apt-repository "deb http://i-hate-farms.github.io/spores trusty main"
sudo apt-get update
```

## How to create the repository

Taken from [those](http://doc.ubuntu-fr.org/tutoriel/comment_creer_depot) two [tutorials](http://www.tecmint.com/create-deb-pacakge-repository-in-ubuntu/)

```
    sudo apt-get install reprepro

    git clone git clone git@github.com:I-hate-farms/spores.git
    cd spores
    git checkout gh-pages
    mkdir -p ./conf
    mkdir -p ./incoming
    # edit the distributions as specified in the tutorials
    gedit ./conf/distributions
    # copy files to incoming
    # Update the repository
    reprepro -Vb . includedeb trusty incoming/*.deb
```

## How to publish
