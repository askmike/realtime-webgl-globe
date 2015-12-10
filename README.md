# Realtime Webgl Globe

A webgl earth making it easy to add custom shapes at coordinates in realtime.

![example gif](http://mikevanrossum.nl/stuff/realtime-webgl-globe/realtime-globe.gif)

[Demo](http://mikevanrossum.nl/stuff/realtime-webgl-globe/example.html)!

## Features

- Makes it easy to add custom shapes to the globe at lat/long positions.
- Interactive (mousewheel scroll & mouse drags).
- Easy API for adding elements on the globe while it's running.

## Basic Usage

    var div = document.getElementById('globe');
    var urls = {
      earth: 'img/world.jpg',
      bump: 'img/bump.jpg',
      specular: 'img/specular.jpg',
    }

    // create a globe
    var globe = new Globe(div, urls);

    // start it
    globe.init();

    // random data
    var data = {
      color: '#FF0000',
      size: 20,
      lat: 52.3747158, // Amsterdam!
      lon: 4.8986231,  // Amsterdam!
      size: 20
    };

    // add a block on Amsterdam
    globe.addBlock(data);

## API

<a name="Globe"></a>
## Globe(container, urls)
Realtime Globe is a WebGL based earth globe that
makes it super simple to add shapes in realtime
on specific lat/lon positions on earth.

**Kind**: global function  

| Param | Type | Description |
| --- | --- | --- |
| container | <code>HTMLElement</code> |  |
| urls | <code>Object</code> | URLs of earth images |
| urls.earth | <code>String</code> |  |
| urls.bump | <code>String</code> &#124; <code>undefined</code> | (optional) |
| urls.specular | <code>String</code> &#124; <code>undefined</code> | (optional) |


* [Globe(container, urls)](#Globe)
  * [.init()](#Globe.init)
  * [.zoomRelative(delta)](#Globe.zoomRelative) ⇒ <code>this</code>
  * [.zoomTo(altitute)](#Globe.zoomTo) ⇒ <code>this</code>
  * [.zoomImmediatelyTo(altitude)](#Globe.zoomImmediatelyTo) ⇒ <code>this</code>
  * [.center(pos)](#Globe.center) ⇒ <code>this</code>
  * [.centerImmediate(pos)](#Globe.centerImmediate) ⇒ <code>this</code>
  * [.addLevitatingBlock(data)](#Globe.addLevitatingBlock) ⇒ <code>this</code>
  * [.addBlock(data)](#Globe.addBlock) ⇒ <code>this</code>
  * [.removeAllBlocks()](#Globe.removeAllBlocks) ⇒ <code>this</code>

<a name="Globe.init"></a>
### Globe.init()
Initializes the globe

**Kind**: static method of <code>[Globe](#Globe)</code>  
<a name="Globe.zoomRelative"></a>
### Globe.zoomRelative(delta) ⇒ <code>this</code>
Zoom the earth relatively to its current zoom
(passing a positive number will zoom towards
the earth, while a negative number will zoom
away from earth).

**Kind**: static method of <code>[Globe](#Globe)</code>  

| Param | Type |
| --- | --- |
| delta | <code>Integer</code> | 

<a name="Globe.zoomTo"></a>
### Globe.zoomTo(altitute) ⇒ <code>this</code>
Transition the altitute of the camera to a
specific distance from the earth's core.

**Kind**: static method of <code>[Globe](#Globe)</code>  

| Param | Type |
| --- | --- |
| altitute | <code>Integer</code> | 

<a name="Globe.zoomImmediatelyTo"></a>
### Globe.zoomImmediatelyTo(altitude) ⇒ <code>this</code>
Set the altitute of the camera to a specific
distance from the earth's core.

**Kind**: static method of <code>[Globe](#Globe)</code>  

| Param | Type |
| --- | --- |
| altitude | <code>Integer</code> | 

<a name="Globe.center"></a>
### Globe.center(pos) ⇒ <code>this</code>
Transition the globe from its current position
to the new coordinates.

**Kind**: static method of <code>[Globe](#Globe)</code>  

| Param | Type | Description |
| --- | --- | --- |
| pos | <code>Object</code> | the position |
| pos.lat | <code>Float</code> | latitute position |
| pos.lon | <code>Float</code> | longtitute position |

<a name="Globe.centerImmediate"></a>
### Globe.centerImmediate(pos) ⇒ <code>this</code>
Center the globe on the new coordinates.

**Kind**: static method of <code>[Globe](#Globe)</code>  

| Param | Type | Description |
| --- | --- | --- |
| pos | <code>Object</code> | the position |
| pos.lat | <code>Float</code> | latitute position |
| pos.lon | <code>Float</code> | longtitute position |

<a name="Globe.addLevitatingBlock"></a>
### Globe.addLevitatingBlock(data) ⇒ <code>this</code>
Adds a block to the globe. The globe will spawn
just below the earth's surface and `levitate`
out of the surface until it is fully `out` of the
earth.

**Kind**: static method of <code>[Globe](#Globe)</code>  

| Param | Type | Description |
| --- | --- | --- |
| data | <code>Object</code> |  |
| data.lat | <code>Float</code> | latitute position |
| data.lon | <code>Float</code> | longtitute position |
| data.size | <code>Float</code> | size of the block |
| data.color | <code>String</code> | color of the block |

<a name="Globe.addBlock"></a>
### Globe.addBlock(data) ⇒ <code>this</code>
Adds a block to the globe.

**Kind**: static method of <code>[Globe](#Globe)</code>  

| Param | Type | Description |
| --- | --- | --- |
| data | <code>Object</code> |  |
| data.lat | <code>Float</code> | latitute position |
| data.lon | <code>Float</code> | longtitute position |
| data.size | <code>Float</code> | size of the block |
| data.color | <code>String</code> | color of the block |

<a name="Globe.removeAllBlocks"></a>
### Globe.removeAllBlocks() ⇒ <code>this</code>
Remove all blocks from the globe.

**Kind**: static method of <code>[Globe](#Globe)</code>  
