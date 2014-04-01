Creating a pattern for diagrams gthat require a bit of circuit style visualization.

* So we go sortest path or not.
* If we change object's positoin, do the wiring/lines automatically realign?
* Paths/wiring will have configurations ...  e.g width / smoothing curve.
* Layouts (shortest distance, relation between objects, length of path)
* Force (pi nnned objects).
* Collision detection
* Treat the problem as a graph and for detecting path intersections use this as example: http://www.jasondavies.com/planarity/
Mike Bostocks Spline Editor: http://bl.ocks.org/mbostock/4342190
* yfiles is the only solution as of yet. And its expensive.

> Goals
- semi-fixed layouts with path layout

> Applications
- network management
- economic flows
- circuit diagram
- game players

> Requirements
- move objects (drag and drop, snapto)
- paths (width, smoothing curves)
- layout (shortest distance, relation between objects, path length)
- force (pinned objects, movement into place)

> Use Case
- create
- movement into place
- describe
- connect
- improve

> Existing Blocks
- spline editor
- directed graph editor
- yfiles circuit layout (loading latency problem)

> Strategy
- focus on primitives
- example: line has describe, curve, layout


Participants:
* shobhitg
* jxstanford
* kenpenn
* stewartnoyce
* yanghung
* mtodd
