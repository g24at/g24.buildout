
TODO
----

visueller editor:

add -> reply und übersetzen
padding vom textfeld links und rechts ein paar pixel

OK auto skalierung von bildern auf 100% (- pixel)
placeholder - für datetime

mobile
tastaturlayout für email, web, zahlenfelder/datumsfelder


design
breit statt hoch, logo in der seite. --> bilschirme gehen in die breite anstatt
höhe wie früher

optisch kennzeichnen: event, thread, ...

http://pypi.python.org/pypi/plone.app.memberschema

autoresize textarea
https://github.com/xing/wysihtml5/issues/18
  http://documentcloud.github.com/underscore/
  http://svn.plone.org/svn/collective/collective.js.underscore/trunk/
  http://pypi.python.org/pypi/collective.js.underscore
 https://github.com/mmonteleone/jquery.flextarea  
https://github.com/jerryluk/jquery.autogrow
https://github.com/azoff/AutoResize
http://james.padolsey.com/javascript/jquery-plugin-autoresize/






next:

    id generation - uuid
        6 stellen                                   
        A-Z,a-z,0-9 = (26+26+10)^6 = 62^6 = 56800235584 ~ 56800 *10^6 ~ 57 *10^9  RTdg76
                                ^4 =           14776336 ~  15 *10^6               RTdg
                       26^6 =                 308915776 ~ 309 *10^6               RTDGWA
                       26^4 =                    456976 ~ 0.5 *10^6               RTDG

    autocomplete widget:
        jqueryui or autosuggest widget?
        use subject vocabulary
        use # notation: typing # starts autocompletion
            parse #words then and index them

    datepicker:
        jquerytools one

    recurrenceinput:
        widgetless javascript integration

OK    textarea:
OK        img autolinker overloading
OK        embedly integration

    location:
        is_event .. autocomplete widget + reference
        no hit: new location + location fields

    organizer: same

    fileupload ajax widget
        only owner of content type can upload files directly in context
        forces to always create enveloping content


    depend on CMFPlone, but not Plone. do not include default profile. create
    a own profile.

    create theme
        use resource bundles to include only resources of interest
        create own main_template
        find way to apply theme only for specific domains, so that normal plone
        is always available

    include teaser

    configure portlets

    create home directories




move bootstrap/editor packages outside this one.

use is_thread on IBasetype to calculate, if content is a thread or not.
        # If posting has more than 2 children: True
        # If not: False


yafowil error handlers in html form?
validation?
use content provider
yafowil js inclusion in sharingbox template instead of portal_javascript

portlets in ~home folders ->
    user configurable
    default portlets override with layer and permission setting

edit form
    static vs dynamic
    derive from addform/editform
        first: apply behaviors
        if, provide custom template here

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


one ranger per termit tab/folder :)



eventually avoid usage of getObject in page templates more aggresively


ResourceRegistry js_registry, css_registry, kss_registry
    upgrade to unreleased 2.1a (bundles concept)
    create g24 theme/browserlayer
    switch theme for user (in Manager group) / allow Manager user to switch theme
    disable as much as possible in registries for g24 skin/theme/browserlayer
    register viewlets for specific browserlayer, show them only for specific theme


@user
#tag
titel*2010,10,10 10:00%location


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
