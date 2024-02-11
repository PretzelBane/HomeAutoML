# HomeAutoML
Exploratory attempt to export targeted data from Hubitiat and use it in ML algorithm to determine desired lighting conditions.
Instead of having to formulate rules in the home automation hub (Hubitat), this will use sensor and other data to predict desired result - a 'learning' model of sorts.

This is just a sandbox right now.  I'm not sure if it will work or how best to do it.  Just trying to get some of the components working first.

Hubitat used a version of Groovy for its internal application development.
I will start with that and try to produce a map of factors:values that can be exported for further processing.
Probably export to a spreadsheet or csv for now.
Target will be one room of my house.

A methodology will have to be devices where Hubitat prompts a user to indicate desired lighting condition (more likely, if the actual condition is desirable or not)
Alternatively, user could initiate this step, but that may lead to bias.
Not sure how to do this in-app yet.  Text notification, perhaps.

Some automatic cleaning of the export may be required

Then export will be fed into a ML alogrithm, probably in Python.
Not sure which model yet.
Probably not Bayes because the variables will almost surely contain dependencies
Maybe a decision tree as that might be easiest to feed back to Hubitat.

Then the model will have to be converted into a ruleset that Hubitat can follow and pushed back to the app.
It's unlikely the ML can be applied in real-time due to processing lag so it will have to be updated outside of normal use, thus the Hubitat-friendly model.
This step could be limiting as I'm not sure how to get it into Hubitat. That's where a decision tree with 'rules' might be most convenient (though maybe not most accurate)
