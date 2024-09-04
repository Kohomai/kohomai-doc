---
layout: default
title: 3. Amplitude with GTM
parent: Tracking setup
nav_order: 3
description: "Sending events from Google Tag Manager to Amplitude"
---
{% include variables.md %}
{% raw %}

# Amplitude with GTM

[Amplitude]'s script has to be "loaded" by [Google Tag Manager] each time a user navigates in your website / webapp.

# Initialisation
In [Google Tag Manager], create the following tags with type ``Amplitude Analytics Browser SDK`` :
- "Amplitude - init" :
	* Tag type : ``Initialize (init)``
	* API Key : ``{{Amplitude - API key}}``
	* Triggering : ``Initialisation - All Pages``

By default, session tracking is activated : we strongly recommend to keep it activated.
If your [Amplitude] project is in the EU, check the "EU" checkbox in the tag configuration.

Use the "Preview" mode in GTM to check that Amplitude is well initialized in all pages. In [Amplitude]'s real time view, you should see some events. 

# Troubleshooting

Depending on the technology of your website / webapp, it might happen that the "Amplitude - init" tag is not triggered on all pages. This is a common issue when only a part of the page is updated (SPA, ajax, reactive apps...).
In that case, try to use the ``History Change`` trigger instead of ``Initialisation - All Pages``

# Next step >>

[4. Pushing events to GTM](/pages/GTM/Events)

{% endraw %}