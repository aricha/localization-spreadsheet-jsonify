localization-spreadsheet-jsonify
================================

A Google App Script that lets you easily access a localization/translation 
Google spreadsheet in JSON format. In other words, you can put together a 
string translation table in Google Docs, and this script will export it
to JSON for you with a minimum of effort.

Step 1
------

Make spreadsheet like this one:

<a href="https://docs.google.com/spreadsheet/ccc?key=0AqrUvD5TZZs3dF9ULUh5X1JlakVJRGFHaWRZQmFuZEE">https://docs.google.com/spreadsheet/ccc?key=0AqrUvD5TZZs3dF9ULUh5X1JlakVJRGFHaWRZQmFuZEE</a>

Step 2
------

**Export it to JSON**:

<a href="https://script.google.com/macros/s/AKfycbxLnEUyElPtL01qHnL7pD2hmTmaO7Tc1yLhjJzQpitpuBfxxBU/exec?sheet%5fid=0AqrUvD5TZZs3dF9ULUh5X1JlakVJRGFHaWRZQmFuZEE&sheet%5fname=Main">https://script.google.com/macros/s/AKfycbxLnEUyElPtL01qHnL7pD2hmTmaO7Tc1yLhjJzQpitpuBfxxBU/exec?sheet%5fid=0AqrUvD5TZZs3dF9ULUh5X1JlakVJRGFHaWRZQmFuZEE&sheet%5fname=Main</a>

**Export it to Django locales (gettext .po catalogs)**:

1. Copy the *contents* of the gettext/ folder to your Django app folder.
-  Edit localize-django-app.py, set SOURCE_URL to your JSONified spreadsheet URL, and run.
-  Run django-admin.py compilemessages
-  Restart your Django instance.
-  Done.

**Export it to [jquery.localize](https://github.com/coderifous/jquery-localize) styled JSON files**:

1. Copy the *contents* of the jquery.localize/ folder to wherever you're trying to serve translations.
-  Edit generate-language-pack.py, set SOURCE_URL to your JSONified spreadsheet URL, and run.
-  Copy the translation-*.json files to the folder where you'll be serving your page.
-  Follow the instructions of [jquery.localize](https://github.com/coderifous/jquery-localize), it should pull in the JSON translation files you've just generated.
-  i.e. Something like $('[data-localize]').localize('translation');

<a href="http://vilimpoc.org/research/LSJ">Here's an example</a> of jquery.localize in action.

**Export it to Cocoa .strings files**:

1. Copy the localize-strings.py to your project folder.
-  Edit localize-strings.py, setting SHEET\_ID to the ID of your Google Spreadsheet, and SHEET\_NAME to the name of the sheet used in that Google Spreadsheet.
-  Run localize-strings.py, optionally specifying an output directory as the first argument.
-  Done.

**Export it to ZIP**: (work in progress)

Unavailable until Google fixes their ContentService so it doesn't mangle 8-bit "application/zip" or "application/octet-stream" output. :(

More Info
---------

To see more info about invoking the app, go to:

<a="https://script.google.com/macros/s/AKfycbxLnEUyElPtL01qHnL7pD2hmTmaO7Tc1yLhjJzQpitpuBfxxBU/exec">https://script.google.com/macros/s/AKfycbxLnEUyElPtL01qHnL7pD2hmTmaO7Tc1yLhjJzQpitpuBfxxBU/exec</a>
