TODO
====

https://github.com/patik/within-viewport
   http://stackoverflow.com/questions/9951072/change-class-based-on-page-scroll 
    https://github.com/sxalexander/jquery-scrollspy
http://imakewebthings.com/jquery-waypoints/
http://stackoverflow.com/questions/12470645/change-css-class-after-scrolling-1000px-down
http://stackoverflow.com/questions/16237953/changing-classes-with-animation-depending-on-scroll-position
http://stackoverflow.com/questions/1548765/swap-css-class-on-the-basis-of-scroll-position-with-javascript/1548869#1548869
http://css-tricks.com/forums/topic/how-to-change-css-class-on-page-scroll-using-jqueryjavascript/
http://getbootstrap.com/2.3.2/javascript.html#scrollspy

http://de.wikipedia.org/wiki/Soundex
   http://en.wikipedia.org/wiki/Soundex 
    http://www.sound-ex.de/

http://en.wikipedia.org/wiki/Geocoding
http://leafletjs.com/reference.html#map-constructor
http://geojson.org/
    http://en.wikipedia.org/wiki/GeoJSON
    http://leafletjs.com/examples/geojson.html
    http://geojson.io/#map=2/20.0/0.4

http://g24.adm.at/
http://plone.github.io/mockup/dev/
https://github.com/plone/mockup/tree/master/js/patterns

http://momentjs.com/
http://momentjs.com/docs/

http://masonry.desandro.com/
http://designshack.net/tutorialexamples/masonry/demos/css.html
http://isotope.metafizzy.co/

* align wysihtml5_g24_rules with parser rules from bootstrap-wysihtml5
* make sure, parser rules are loaded
* pass options to wysihtml5: autoLink, allowObjectResizing, etc.

* load plone.app.event standard js and FIX it (or use bootstrap overlay in
  calendar portlet).
* style shareingbox edit form

* create yafowil widgets:
  - select2
  - leaflet maps
  - jquery fileupload
  - jquerytools datepicker

* jquery globalize?










==================================================================


mandatory tags, user tags
eventuell versch. ebenen von tags, kontext zu mandatory tags (musik ->
styles...))
event-> publish to kulturserver

next: alpha phase
----

    plone.app.event integration
        datepicker
        recurrenceinput
        fullcalendar

    VIEWS
        g24.at/thread/12345
        g24.at/stream/12345
        g24.at/calendar/2011-11-11
                       /2011-11
                       /01-52

        3 parent posts
        paging

    g24 user migration
    g24 content migration

    g24 theme integration
        logo
        farben

    theme
        remove edit bar for specific theme, use other theme for different url
            or remove edit bar, ... for normal users

    #tags, @user

VIEWS
-----

    url schema:
        g24.at/~thet .. home directories
        g24.at/stream/123456
        g24.at/thread/123456
        g24.at/calendar

    über-tags:
        kultur, musik, politik, allgemein
        redaktionelle zusammenfassung mehrerer tags in kategorien



SHARINGBOX
----------

    cancel button

    dirty warning

    autocomplete widget:
        jqueryui or autosuggest widget?
        use subject vocabulary
        use # notation: typing # starts autocompletion
            parse #words then and index theme

        #tag
        @user
        titel*2010,10,10 10:00%location

    datepicker:
        jquerytools one

    recurrenceinput:
        widgetless javascript integration

    location:
        is_event .. autocomplete widget + reference
        no hit: new location + location fields

    organizer: same

    fileupload ajax widget
        only owner of content type can upload files directly in context
        forces to always create enveloping content


ELEMENTS
--------

    use is_thread on IBasetype to calculate, if content is a thread or not.
        # If posting has more than 2 children: True
        # If not: False


THEME
-----

    remove clutter for theme
        no edit bar
        remove unn. portlets & viewlets

    create theme
        use resource bundles to include only resources of interest
        create own main_template
        find way to apply theme only for specific domains, so that normal plone
        is always available

    develop g24 styles


USERs / PROFILES
----------------

    create home directories  g24.at/~thet --> traverser

    user data fields
        http://pypi.python.org/pypi/plone.app.memberschema



INTEGRATiON
-----------

    depend on CMFPlone, but not Plone. do not include default profile. create
    a own profile.

    include teaser

    configure portlets

    move bootstrap/editor packages outside this one.


thomas
------
    visueller editor:
        add -> reply und übersetzen
        padding vom textfeld links und rechts ein paar pixel

        OK auto skalierung von bildern auf 100% (- pixel)
        placeholder - für datetime

    mobile
        tastaturlayout für email, web, zahlenfelder/datumsfelder

    design
        breit statt hoch, logo in der seite. --> bilschirme gehen in die breite anstatt in die höhe wie früher

    optisch kennzeichnen: event, thread, ...


PLIPs & ZIPs & OWN
------------------
    zope svn -> github (mirror?)

    OK one ranger per termit tab/folder :)


DONE
----

OK elements: use content provider

OK    textarea:
OK        img autolinker overloading
OK        embedly integration
OK        asynchronous embedly integration

OK    id generation - uuid
        6 stellen
        A-Z,a-z,0-9 = (26+26+10)^6 = 62^6 = 56800235584 ~ 56800 *10^6 ~ 57 *10^9  RTdg76
                                ^4 =           14776336 ~  15 *10^6               RTdg
                       26^6 =                 308915776 ~ 309 *10^6               RTDGWA
                       26^4 =                    456976 ~ 0.5 *10^6               RTDG

OK/2    autoresize textarea
    https://github.com/xing/wysihtml5/issues/18
        http://documentcloud.github.com/underscore/
        http://svn.plone.org/svn/collective/collective.js.underscore/trunk/
        http://pypi.python.org/pypi/collective.js.underscore
    https://github.com/mmonteleone/jquery.flextarea
    https://github.com/jerryluk/jquery.autogrow
    https://github.com/azoff/AutoResize
    http://james.padolsey.com/javascript/jquery-plugin-autoresize/


OK: YAFOWIL
    edit form
        static vs dynamic
        derive from addform/editform
            first: apply behaviors
            if, provide custom template here



yafowil error handlers in html form?
validation?
yafowil js inclusion in sharingbox template instead of portal_javascript


portlets in ~home folders ->
    user configurable
    default portlets override with layer and permission setting
    
    portlets are contextural configurable! how cool is this? make portlets
    configurable for users within their homefolder ..... well, you can't allow
    users to edit any portlets on any context ... but you can!



behaviors
    index on feature (behavior name) or indexed behavior interfaces (favorite, check)
    for every feature one behavior:
    home folder
        traverser /~username
    event
    location
    organizer
    workflow
        change workflow state here
    title
    features
        is event
        is location
        is title



eventually avoid usage of getObject in page templates more aggresively


ResourceRegistry js_registry, css_registry, kss_registry
    upgrade to unreleased 2.1a (bundles concept)
    create g24 theme/browserlayer
    switch theme for user (in Manager group) / allow Manager user to switch theme
    disable as much as possible in registries for g24 skin/theme/browserlayer
    register viewlets for specific browserlayer, show them only for specific theme



* plone.app.jquery/master depends on P.ResourceRegistry with "bundle" feature.
  branch 1.4 does not. document, depend on p.resreg or fix it in p.a.jq.


* let users log in via jabber, remove the need of registering via plone first

* sharing box. embedly service über eigenes feld.

* Solgema.fullcalendar


Sharing Box
-----------

- Klick Checkbox -> ajax request: set_event. response on success: wether html
  form, or json string, which describes the form.

- Javascript form library. HTML Templates as HTML templates, retrieved from
  server via some resource request.
