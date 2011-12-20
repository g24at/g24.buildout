g24.buildout installation
=========================

Install dependencies
--------------------

erlang
libpcre3-dev
libxml2-dev
libxslt1-dev


Install
-------

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


Configure
---------

$ ./bin/ejabberdctl register admin localhost your_password
Check: http://localhost:5280/admin
       http://localhost:5280/http-bind

Start xmpp server
$ ./bin/ejabberd

Start nginx server
$ ./bin/frontend start

Start Zope instance
$ ./bin/instance fg

Create Plone Site: http://localhost:8080/manage
Edit registry settings in controlpanel. jarn.xmpp.* 
Restart Plone
Admin Login
Setup PubSub nodes
http://localhost:9000/@@setup-xmpp


Run
---

1) start ejabberd
2) start nginx
3) start instance
