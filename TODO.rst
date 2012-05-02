
TODO
----
http://pypi.python.org/pypi/plone.app.memberschema


next:
    autocomplete widget:
        jqueryui or autosuggest widget?
        use subject vocabulary
        use # notation: typing # starts autocompletion
            parse #words then and index them

    datepicker:
        jquerytools one

    recurrenceinput:
        widgetless javascript integration

    textarea:
        img autolinker overloading
        embedly integration

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
