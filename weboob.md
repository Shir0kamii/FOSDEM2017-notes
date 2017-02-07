Weboob
======

"The web is about transmitting information to everyone regardless of the
platform" - Tim Berner Lee

problem
-------

People usually use a browser and the web is broken if you don't run javascript.

To use the web correctly outside of a browser, we need to simulate the browser
to load javascript and style.

eg. `something $url | grep ... | cut` vs copy-pasting after scrolling

Solution
--------

Build an interface to do just that: *Weboob*

implementation
--------------

Implementing interactions with a websites is always done by subclassing a set
of classes. Most of the code is declarative as everything is modular in the
mother class.

You even have scripts to generate a skeleton for a new website implementation,
depending on the capabilities you want to implement.

Prefer structured data sources over raw HTML.

### Capabilities

A website implementation implements capabilities. these are for example search
or login, or banking.

### Browser

The browser subclass implements the different interactions possible with the
website.

### Page

You must implement a page for each kind of page the browser interacts with.

### Module

The module is used as a glue between all functions of the websites. It uses
the browser class on pages to get the results you want.

Why use Weboob ?
----------------

Reuse unix tools on data from these websites.
You can automate tasks.

Command line applications are already written using Weboob:
 * QBooblyrics, to get lyrics
 * QCineoob, to get all informations about movies, including subtitles and
torrents
 * QFlatBoob, to help with housing research
 * QHandjoob, search for a job
 * Comparoob, to compare prices for a product
 * Geolooc, Geolocalize IP address
 * Translaboob, to translate text

Many website implementation are already written.
Some existing modules:
 * github
 * redmine
 * Many french banks
 * shipping websites
 * youtube
 * linuxjobs
