# PCF Roadmap Landing Page

The landing page is an HTML file that is fronted by the vanity URL described in the next section. With every new PCF (PAS or PKS) release, actions should take place.  If there was a new PAS release, for example, you would need to rotate the decks.  the previous release roadmap deck would need to be added to the archive section and the new deck would be added as the main URL.  For example if PAS latest was 2.0 and 2.1 deck was just created::

1.  edit archive.html and add a new reference for the 2.0 deck (note the list is ascending with newest at top)
2.  edit /pcf-pas-roadmap-redirect/manifest.yml to point to the gdoc url of the new 2.1 deck
3.  cf push the pcf-pas-roadmap-redirect app with the updated manifest


## Redirect app for the PCF Roadmap

This little Cloud Foundry application does a simple redirect from a vanity URL to a URL configured in the manifest.yml. Note that if the URL is a google doc, that you should append a '?' to the end or the URL may not load properly.

It uses the [staticfile buildpack](https://github.com/cloudfoundry/staticfile-buildpack) to deploy a bespoke `nginx.conf`. That's it.

## Deploy

```
# Update manifest.yml to have the right URL to redirect to.
# Login as a user with access to PWS jwatters-org / staging space.
cf push
```
