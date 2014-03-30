# Hacks, tips, and tricks

_(a disorganized collection of random notes)_

* When picking color palettes, try using HSL and avoid having two with the same luminance, to make them easier to distinguish
* Don't forget monitor hardware differences, Windows/Mac differences in color!
* jQuery caches things it selects from the DOM, which can fall out of sync when you're adding/removing with D3!
* Angular + D3 can get slow above thousands / 10k SVG nodes
* border-radius can be a hit on performance!
* transparent SVG elements can be click targets! (maybe put things in a &lt;g> and then create another element)
* In Chrome inspector, click timeline > frames! for performance debugging! (shows JS and render time)
* c.f. paul irish: http://www.paulirish.com/2011/a-re-introduction-to-the-chrome-developer-tools/
* Sometimes it's better to set visibility -> null or opacity -> null rather than visible/1.0 or other defaults (for SVG performance)
* &lt;g> tags are powerful and underused, for keeping SVG organized, and e.g. for transforms! (normally you only get one transform per element, so use multiple groups!) ... also, transforms are usually faster when done on &lt;g> elements
* bostock's demo: http://bl.ocks.org/mbostock/3680999 and http://bl.ocks.org/mbostock/3680957
* trick: when appending elements, the name/type of element (path, group etc.) can be a function of the data
* for performance tuning, look at repaint/reflow events, minimize those
