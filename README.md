silverstripe-searchable
=======================

Adds to the default Silverstripe search by adding a custom results
controller and allowing properly adding custom data objects and custom
fields for searching 

## Installation
Install this module either by downloading and adding to:

[silverstripe-root]/searchable

Then run: http://yoursiteurl.com/dev/build/

Or alternatively add to your projects composer.json

## Usage

To add your object to the search results, you need to make Searchable
aware of it. Do this by adding the following to your _config.php:

    Searchable::add("ObjectClass", array("Col1","Col2"), "Friendly Title");

This will then add the object to Searchable's searchable classes.

For example, you can add SiteTree using the following:

    Searchable::add("SiteTree", array("Title","MenuTitle","Content","URLSegment"), "Pages"); 

## Results Dashboard

As Searchable can display results for multiple types of object, the
default interface used to display these objects is the "dashboard".

The dashboard displays a summary of results for each object and
generates a view more link to display more of that type of post (for
example, more products, more forum posts, etc).

You can customise how many items are displayed on the dashboard with the
config variable:

    Searchable.dashboard_items

If searchable is only setup for one type of object, the dashboard will be
disabled and instead the user will be taken directly to a search results
page for that object.

## Custom search templates

By default the search results are rendered into two templates:

    SearchResults.ss
    
Or

    SearchResults_object.ss

The former controls the apperance of the dashboard, the latter
controls the apperance of the results for a particular object.

You can further customise how the results appear on an object specific
bases by adding a template named after the object in question, for
example:

    SearchResults_Product.ss
    
The above would be used to display only search results for a product
object.
