
TODO
----
http://pypi.python.org/pypi/plone.app.memberschema

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
