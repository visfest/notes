# Overview
 Filters allow for additional visual effects, such as blur. The most obvious use of filters is to enhance a visualization's aesthetics, or o create data "art." Filters can be used as their own dimension for encoding data - for example, accuracy, precision, or confidence could e represented by a blur filter; the strength of the blur representing the confidence of the data.
 
 Most things you can do in photoshop for filter effects you can do with SVG. [Inkscape](http://www.inkscape.org/en/) can help you xperiment/play with filters with a UI before going for code.
 
 
 All the inkscape filters can be done in svg. Inkscape was built to do standardized SVG.  Illustrator was built before standardized SVG -  lot of the illustrator filters are not in the specification and will just be rasterized.
 
 
 The filters that stack is really hard to get right with just javascript, but you can get it right in inkscape and export it into omething your D3 visualization can consume.
 
## General Filter Usage Overview
 
Add a `<defs>` tag and define a filter within. A filter tag has (at least) two attributes: `in` and `out`. These specify which "image" r "layer" to apply the filter to. `SourceGraphic` is a reserved word that references the graphical elements that were the original input nto the `<filter>` element
 
 ```
 var defs = svg.append('svg:defs');
 var filterBlur = defs.append('svg:filter').attr({ id: 'blurFilter' });
 filterBlur.append('feGaussianBlur').attr({
           'in': "SourceGraphic",
           'stdDeviation': 20
     });
 ```
 
 * Use the filter attribute on an element to refer back to the filter id you defined; e.g., `<rect filter="url(#blurFilter)"></rect>`
 
## Examples
 **Specific examples**
 
 * [Blur / Fade Wet Window Effect](http://bl.ocks.org/enoex/9626212). Two images - one is blurred, one is not 
 * [Using filters to turn bad vis into attractive data art](http://guildwars2viz.com/)
 * [Coffee Stain effect](https://dl.dropboxusercontent.com/u/55434504/CoffeeStain_collection.svg)
 
 **General**
 
 * [SVG Filter Gallery](https://dl.dropboxusercontent.com/u/55434504/SVG_Gallery.html)
 * [SVG Filter Effects for Text](https://dl.dropboxusercontent.com/u/55434504/text_effects1.svg)
 * [SVG filter templates](https://github.com/roundrobin/d3-svg-filter-templates)
 
 
## Resources
 * [Book recomendation for learning SVG](http://commons.oreilly.com/wiki/index.php/SVG_Essentials)
 * [SVG Filters spec](http://www.w3.org/TR/SVG11/filters.html)
 * [Intro to filters](http://www.w3schools.com/svg/svg_filters_intro.asp)
 
## Utilities
 
 * [Utiltiy to clean up SVG files, remove generated content from Illustrator / Inkscape](https://github.com/svg/svgo)
 * [Dat GUI - library for playing with variables](https://code.google.com/p/dat-gui/)
 
## Contacts
 * [@enoex](https://twitter.com/enoex) | [github](https://twitter.com/enoex)
 * [@BausOfTheNauf](https://twitter.com/bausofthenauf) | [github](https://github.com/roundrobin)
