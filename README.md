# Spores
[Spores](http://i-hate-farms.github.io/spores) is the ppa for all our applications and libraries

## How to install the ppa...
... and get all the nice applications! 
```
wget -O -  http://i-hate-farms.github.io/spores/key/deb.gpg.key | sudo apt-key add - 
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
    reprepro --ask-passphrase  -Vb . includedeb trusty incoming/*.deb
```
## Signing the repository 
Following this [tutorial](http://www.tecmint.com/create-deb-pacakge-repository-in-ubuntu/)
```
cd spores
sudo apt-get install gnupg
mkdir -p ./key
gpg --gen-key
reprepro --ask-passphrase -Vb . export
```

## How to publish new deb package
```
cd spores
reprepro --ask-passphrase -Vb . includedeb Trusty /home/ravisaive/packages.deb
```
