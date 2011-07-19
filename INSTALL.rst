g24.buildout installation
=========================

$ git clone git@github.com:thet/g24.buildout.git g24.buildout
$ cd g24.buildout
$ mkdir src
$ cd src
$ git clone git@github.com:thet/buildout-base.git
$ cd ..

$ virtualenv --no-site-packages --distribute python
$ source python/bin/python
$ python bootstrap.py -d -c dev.cfg
$ ./bin/buildout -c dev.cfg

