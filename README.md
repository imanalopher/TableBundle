README
======

What's KilikTableBundle ?
--------------------------
KilikTableBundle is a fast, modern, and easy-to-use way to manipulate paginated 
information, with filtering and ordering features, with ajax queries.

This bundle is a work in progress.

Links:
------
- [Live demo](http://tabledemo.kilik.fr/)
- [KilikTableDemoBundle](https://github.com/KilikFr/TableDemoBundle)

Working features:
-----------------
- pagination
- basic filtering (like %...%)
- advanced filtering (<,>,<=,>=,=,!,!=)
- ordering by column (and reverse)
- basic table template extendable
- keep filters and orders in browser local storage (api REST)
- filtering on queries with group by
- show ordered column (normal and reverse)
- max items per page selector (customizable)
- delay on keyup events (to prevent multiple reloads)
- checkbox and select filter
- CSV export of filtered rows
- customization of visible columns (hide/show checkboxes)
- column display callback
- multiple lists on one page
- pre-load default filters and reset local storage filters
- smart filtering on many words (Filter::TYPE_LIKE_WORDS_AND)

Planned features:
------------------
- more translations
- add advanced templates
- loading image waiting ajax response
- new column display types (now: only raw text value)

Usage
-----

This documentation need to be completed.

Here, some examples to show latest features.

Optimized version to load entities, from Repository Name:

        $table = (new Table())
            // ...
            ->setEntityLoaderRepository("KilikDemoBundle:Product")
            // ...

Optimized version to load entities, from Callback method:

        $table = (new Table())
            // ...
            ->setEntityLoaderCallback(function($ids) {
                return $this->manager()->getRepository('KilikDemoBundle:Product')->findById($ids);
            })
            // ...
