---
layout: default
title: Integration in Bubble
nav_order: 5
description: "How to integrate Kohomai in Bubble"
---
{% include variables.md %}

# How to integrate Kohomai in Bubble

1. Install API plugin

In your [Bubble] app, go to "Plugins" on the left navigation panel, then click on "Add plugins" on the top right of the screen. Search "API Connector" plugin, and click "Install".

2. Configure a new API call

In API Connector plugin page, click on "Add another API", and set the following values :
* API Name : "Kohomai" _(you can use another name)_
* Authentication : Private key in header
* Key name : "Authorization"
* Key value : _paste your API key here_

Click on "Add a shared header", and set :
* Key : "Content-Type"
* Value : "application/json"

Click on "Add another call", and set :
* Name : "Register a lead" _(you can use another name)_
* Use as : Action
* Data type : JSON
* Method : POST
* URL : "https://app.kohomai.com/api/v1/journeys?ref=XXX" _(where XXX is the reference of the API starting point in your funnel)_
* Body type : JSON
* Body : "{"Firstname": "<firstname>", "Lastname": "<lastname>", "Email": "<email>", "RedirectURL": "<redirectURL>"}"
* Body parameters : 4 keys should have been created : firstname, lastname, email, redirectURL ; leave the values empty

3. Insert the API call in your [Bubble] workflow

Go to the workflow you want to use to call Kohomai, and click on "Click here to add an action...". In the drop down menu, go to "Plugins", and select "Kohomai - Register a lead" (or whatever you previously set as a name).
Set the parameters values for the API call in the contextual popup of this step ; if this workflow is triggered from a page containing a form with a field named "firstname", then you would have to use "Input firstname's value" for example.

[Bubble]: https://bubble.io