Tangram: WebGL Maps for Vector Tiles
===

[![Circle CI](https://circleci.com/gh/tangrams/tangram.png?style=badge&circle-token=2529a88125530794f64ffa1783625b5357456f71)](https://circleci.com/gh/tangrams/tangram)

![tangram-header](https://cloud.githubusercontent.com/assets/459970/7569087/8cd14df6-f7d4-11e4-8360-db31790d2bbf.png)

Tangram is a JavaScript library for rendering 2D & 3D maps live in a web browser with WebGL. It is tuned for OpenStreetMap but supports any source of GeoJSON/TopoJSON or binary vector tiles.

## Quickstart

Here's a [simple demo](https://tangrams.github.io/simple-demo/) ([repo here](https://github.com/tangrams/tangram-demo)) with a basic example of a Tangram map. 

The current version of Tangram can be included in your page with:

```
<script src="https://mapzen.com/tangram/0.1/tangram.min.js"></script>
```

The library includes a [Leaflet](http://leafletjs.com) plugin, `Tangram.LeafletLayer`, to provide basic web map pan/zoom functionality.

Data sources, layers, and styling rules are written in a *scene file* ([here's an example](https://github.com/tangrams/simple-demo/blob/gh-pages/scene.yaml)). Armed with a scene file like `scene.yaml`, you can create a Tangram scene and add it to a Leaflet like so:

```
var map = L.map('map');
var layer = Tangram.leafletLayer({ scene: 'scene.yaml' });
layer.addTo(map);
```

## Demos

[**simple-demo**](http://github.com/tangrams/tangram-demo) - A minimal demo showing the basic setup

[**highways-demo**](http://github.com/tangrams/highways-demo) - Zoom-dependent styles and contextual filtering rules

[**gui-demo**](http://github.com/tangrams/gui-demo) - Control styles in real-time with a gui

[**shaders-demo**](http://github.com/tangrams/shaders-demo) - Simple glsl shaders

[**Tangram-sandbox**](http://github.com/tangrams/tangram-sandbox) - More complex glsl shaders

## Vector Tiles

Instead of loading traditional bitmap tiles, Tangram draws its own tiles from scratch, based on **vector tiles** that contain the source data.

Mapzen provides a free [vector tile service](http://mapzen.com/vector/) extracted from for OpenStreetMap base layer data, with worldwide coverage updated daily. There is also an [OSM.US-hosted](http://openstreetmap.us/~migurski/vector-datasource/) alternative.

Tangram currently supports GeoJSON/TopoJSON tiles as well as the [mapnik binary format](https://github.com/mapbox/vector-tile-spec), both of which can be generated by the [Mapzen vector tile service](http://mapzen.com/vector/). (Here's an [example GeoJSON tile](http://vector.mapzen.com/osm/all/14/4826/6161.json).)

## Styling

The *scene file* is where you specify data sources and layers, filter the data, and define and apply styles. (In our demos, this file is named scene.yaml.) The rules for doing these things are many and various, but the basics are pretty easy, and they are all meticulously documented in the Tangram Documentation https://github.com/tangrams/tangram/wiki.

The scene file is written in YAML, which is a data-serialization format like JSON, but with less punctuation. Instead, data structures are specified with whitespace, like Python. One neat side benefit is that the format is super friendly to strings, which means you can write inline JavaScript and GLSL code straight into the scene file, without needing to wrap it in quotes or concatenate anything.

## Documentation

For documentation, see the Tangram[ Documentation wiki](https://github.com/tangrams/tangram/wiki).

For questions, comments, suggestions, or to report a bug, please open a [new issue](https://github.com/tangrams/tangram/issues).

## Contributions Welcome

Tangram is open-source, and we eagerly welcome feedback, feature requests, and contributions. We’re especially interested to see your maps, no matter how simple! Send screenshots, links, and any questions to tangram@mapzen.com.

For instructions, see [CONTRIBUTING.md](CONTRIBUTING.md).
