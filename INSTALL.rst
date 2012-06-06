g24.buildout installation
=========================

Install dependencies
--------------------

$ sudo apt-get install subversion git build-essential
$ sudo apt-get install libreadline-dev zlib1g-dev libbz2-dev
$ sudo apt-get install libssl-dev libjpeg-dev
$ sudo apt-get install libexpat1-dev libpcre3-dev libxml2-dev libxslt1-dev
$ sudo apt-get install erlang erlang-dev
$ sudo apt-get install python-dev libmysqlclient-dev


Install
-------

This project uses git pushurls to have general RO checkout and the possibility
to check in RW at the same time.

$ git clone git@github.com:thet/g24.buildout.git g24.buildout
$ cd g24.buildout

$ virtualenv --no-site-packages --distribute python
$ source python/bin/python
$ python bootstrap.py -d -c dev.cfg
$ ./bin/buildout -c dev.cfg

Eventually remove ejabberd database
$ rm -Rf ./var/ejabberd

Start xmpp server
$ ./bin/ejabberd start

Setup ejabberd admin user
$ ./bin/ejabberdctl register admin localhost YOUR_PASSWORD
Check: http://localhost:5280/admin
       http://localhost:5280/http-bind

Start nginx server
$ ./bin/frontend start

Start Zope instance
$ ./bin/instance fg

Create Plone Site with Profiles applied: "g24.base: development":
http://localhost:8080/@@plone-addsite?site_id=Plone

Import additional profiles to setup content
http://localhost:8080/Plone/portal_setup/manage_importSteps
Profiles:
    "g24.importer postnuke import" (g24 mysql installation required)
    "g24.importer xml import" (g24 xml post export via provided scripts
                               required)

Finally, after the "postnuke import" step and all users are created,
setup the PubSub nodes:
http://localhost:9000/@@setup-xmpp
This step should be done after the batch import of users was made, otherwise
things would take too long.
Users, which are created later are automatically synced.


Visit: http://localhost:9000/Plone



Run
---

1) start ejabberd
2) start nginx
3) start instance
