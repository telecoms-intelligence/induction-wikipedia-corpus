
# References

# Installation

## Python 3

### Ubuntu / Debian
```bash
$ sudo su -
$ apt-get -y install python3-dev python3-pip
```

### Fedora/CentOS/RedHat
* If needed, enable the EPEL repository
```bash
$ su -
$ yum -y install epel-release
```
* Install python34 and python-pip packages (but not virtualenv)
```bash
$ yum -y install python34 python-pip
```
* If needed, uninstall virtualenv
```bash
$ yum remove python-virtualenv
```
* Update pip and install virtualenv with pip
```bash
$ pip install --upgrade pip
$ pip install virtualenv
```

### MacOS
```bash
$ brew install python3
```

## Python virtual environment
* To install the Python 3 virtual environment:
```bash
$ pip install --upgrade pip
$ pip install virtualenv
$ mkdir ~/dev
$ cd ~/dev
$ virtualenv -p python3 venv3
```
* To activate the Python 3 virtual environment:
```bash
$ source ~/dev/venv3/bin/activate
```
* To deactivate the Python 3 virtual environment
```bash
$ deactivate
```

## Library 
```bash
pip install gensim
```

## Data
The Wikipedia snapshot dump file, eventhough it is compressed, takes 13 GB of disk space,
and may take up to 2 hours of downloading time on fast networks (the limitation comes
from the Wikipedia Web servers).
```bash
$ wget https://dumps.wikimedia.org/enwiki/latest/enwiki-latest-pages-articles.xml.bz2
```

# Walkthrough
* Activate the Python virtual environment
```bash
$ source ~/dev/venv3/bin/activate
```

* Build the corpus. That operation takes several hours
```bash
$ python python/make_wiki_corpus.py enwiki-latest-pages-articles.xml.bz2 wiki_en.txt
Processed 10000 articles
Processed 20000 articles
Processed 30000 articles
Processed 40000 articles
Processed 50000 articles
Processed 60000 articles
Processed 70000 articles
Processed 80000 articles
Processed 90000 articles
Processed 100000 articles
...
```

* Check the corpus
```bash
$ python python/check_wiki_corpus.py wiki_en.txt
...
best loved patriotic songs harperresource external links mp and realaudio 
recordings available at the united states library of congress words sheet 
music midi file at the cyber hymnal america the beautiful park in colorado 
springs named for katharine lee bates words archival collection of america 
the beautiful lantern slides from the another free sheet music 

>>> Type 'STOP' to quit or hit Enter key for more <<<
```


