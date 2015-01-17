# Realtime Webgl Globe

A webgl earth making it easy to add custom shapes at coordinates in realtime.

![example gif](http://mikevanrossum.nl/stuff/realtime-bitcoin-globe/realtime-globe.gif)

[Demo](http://mikevanrossum.nl/stuff/realtime-bitcoin-globe/example.html)!

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

## Dependencies

- Three.js (r68+)
- A browser with WebGL support

## API

### Globe(container, urls)

- @param container DOM Node div
- @param urls Object URLs of images:

```{
  earth: String URL  
  bump: Sting URL [optional]  
  specular: String URL [optional]  
}```

Constructor function, creates a globe.

### globe.init()

Spawns the globe.

### globe.zoomRelative(delta)

- @param int delta

Zoom the earth relatively to its current zoom.
(passing a positive number will zoom towards
the earth, while a negative number will zoom 
away from earth).

### globe.zoomTo(altitute)

- @param int altitute

Transition the altitute of the camera to a specific
distance from the earth's core.

### globe.zoomImmediatelyTo(altitute)

- @param int altitute

Set the altitute of the camera to a specific
distance from the earth's core.

### globe.center(coordinates)

- @param Object coordinates:

```{  
  lat: (Float) latitute position,  
  lon: (Float) longtitute position  
}```
 
Transition the globe from its current position
to the new coordinates.

### globe.centerImmediate(coordinates)

- @param Object coordinates:

```{  
  lat: (Float) latitute position,  
  lon: (Float) longtitute position  
}```

Center the globe on the new coordinates.

### globe.addLevitatingBlock = function(data)

- @param Object data:
  
```{  
  lat: (Float) latitute position,  
  lon: (Float) longtitute position,  
  size: (Float) size of block,  
  color: (String) color of block  
}```
   
Adds a block to the globe. The globe will spawn
just below the earth's surface and `levitate`
out of the surface until it is fully `out` of the
earth.

### globe.addBlock(data)

- @param Object data

```{
  lat: (Float) latitute position,  
  lon: (Float) longtitute position,  
  size: (Float) size of block,  
  color: (String) color of block  
}```
 
 Adds a block to the globe.

### globe.removeAllBlocks()

Remove all blocks from the globe.