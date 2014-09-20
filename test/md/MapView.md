##Modules
* [MapView](#module_MapView)
  * [class: MapView ⏏](#exp_module_MapView^MapView)
    * [new MapView(options)](#new_module_MapView^MapView◊)
    * [MapView.DEFAULT_OPTIONS](#module_MapView^MapView.DEFAULT_OPTIONS)
    * [mapView.getMap()](#module_MapView^MapView#getMap)
    * [mapView.setPosition(position, [transition], [callback])](#module_MapView^MapView#setPosition)
    * [mapView.getPosition()](#module_MapView^MapView#getPosition)
    * [mapView.getFinalPosition()](#module_MapView^MapView#getFinalPosition)
    * [mapView.getZoom()](#module_MapView^MapView#getZoom)
    * [mapView.pointFromPosition(position)](#module_MapView^MapView#pointFromPosition)
    * [mapView.positionFromPoint(point)](#module_MapView^MapView#positionFromPoint)
    * [mapView.getSize()](#module_MapView^MapView#getSize)
    * [mapView.halt()](#module_MapView^MapView#halt)
    * [mapView.isActive()](#module_MapView^MapView#isActive)




<a name="module_MapView"></a>
##MapView
MapView encapsulates a Google maps view so it can be used with famo.us.

Additionally it adds methods to set the position and zoom-factor of the map using transitions.
Use `MapModifier` and `MapStateModifier` to place famo.us renderables on the map, much like google-maps markers.

**Map-types**

|Value|Description|
|---|---|
|MapType.GOOGLEMAPS (default)|Google-maps.|
|MapType.LEAFLET|Leaflet.js.|

* [MapView](#module_MapView)
  * [class: MapView ⏏](#exp_module_MapView^MapView)
    * [new MapView(options)](#new_module_MapView^MapView◊)
    * [MapView.DEFAULT_OPTIONS](#module_MapView^MapView.DEFAULT_OPTIONS)
    * [mapView.getMap()](#module_MapView^MapView#getMap)
    * [mapView.setPosition(position, [transition], [callback])](#module_MapView^MapView#setPosition)
    * [mapView.getPosition()](#module_MapView^MapView#getPosition)
    * [mapView.getFinalPosition()](#module_MapView^MapView#getFinalPosition)
    * [mapView.getZoom()](#module_MapView^MapView#getZoom)
    * [mapView.pointFromPosition(position)](#module_MapView^MapView#pointFromPosition)
    * [mapView.positionFromPoint(point)](#module_MapView^MapView#positionFromPoint)
    * [mapView.getSize()](#module_MapView^MapView#getSize)
    * [mapView.halt()](#module_MapView^MapView#halt)
    * [mapView.isActive()](#module_MapView^MapView#isActive)

<a name="exp_module_MapView^MapView"></a>
###class: MapView ⏏
  * [class: MapView ⏏](#exp_module_MapView^MapView)
    * [new MapView(options)](#new_module_MapView^MapView◊)
    * [MapView.DEFAULT_OPTIONS](#module_MapView^MapView.DEFAULT_OPTIONS)
    * [mapView.getMap()](#module_MapView^MapView#getMap)
    * [mapView.setPosition(position, [transition], [callback])](#module_MapView^MapView#setPosition)
    * [mapView.getPosition()](#module_MapView^MapView#getPosition)
    * [mapView.getFinalPosition()](#module_MapView^MapView#getFinalPosition)
    * [mapView.getZoom()](#module_MapView^MapView#getZoom)
    * [mapView.pointFromPosition(position)](#module_MapView^MapView#pointFromPosition)
    * [mapView.positionFromPoint(point)](#module_MapView^MapView#positionFromPoint)
    * [mapView.getSize()](#module_MapView^MapView#getSize)
    * [mapView.halt()](#module_MapView^MapView#halt)
    * [mapView.isActive()](#module_MapView^MapView#isActive)

<a name="new_module_MapView^MapView◊"></a>
####new MapView(options)
**Params**

- options `Object` - Options.  
  - type `MapType` - Map-type (e.g. MapView.MapType.GOOGLEMAPS, MapView.MapType.LEAFLET).  
  - mapOptions `Object` - Options that are passed directly to the Map object. The options should include the 'center' and 'zoom'.  
  - \[id\] `String` - Id of the DOM-element to use. When ommitted, a DOM-element is created using a surface.  
  - \[zoomTransition\] `Transition` - Transition to use for smoothly zooming renderables (by default a transition of 120 ms is used).  

    * [new MapView(options)](#new_module_MapView^MapView◊)

<a name="module_MapView^MapView#isActive"></a>
####mapView.isActive()
Is there at least one action pending completion?

**Returns**: `Bool` - True when there are active transitions running.  
    * [mapView.isActive()](#module_MapView^MapView#isActive)

<a name="module_MapView^MapView#getMap"></a>
####mapView.getMap()
Get the internal map-object. This object may not yet have been initialized, the map is only
guarenteed to be valid after the 'load' event has been emited.

**Returns**: `Map` - Map object.  
    * [mapView.getMap()](#module_MapView^MapView#getMap)

<a name="module_MapView^MapView#setPosition"></a>
####mapView.setPosition(position, [transition], [callback])
Set the center of the map to the given geographical coordinates.

**Params**

- position `LatLng` - Position in geographical coordinates.  
- \[transition\] `Transitionable` - Transitionable.  
- \[callback\] `function` - callback to call after transition completes.  

    * [mapView.setPosition(position, [transition], [callback])](#module_MapView^MapView#setPosition)

<a name="module_MapView^MapView#getPosition"></a>
####mapView.getPosition()
Get the current center position of the map, in geographical coordinates.

**Returns**: `LatLng` - Position in geographical coordinates.  
    * [mapView.getPosition()](#module_MapView^MapView#getPosition)

<a name="module_MapView^MapView#getFinalPosition"></a>
####mapView.getFinalPosition()
Get the destination center position of the map, in geographical coordinates.

**Returns**: `LatLng` - Position in geographical coordinates.  
    * [mapView.getFinalPosition()](#module_MapView^MapView#getFinalPosition)

<a name="module_MapView^MapView#halt"></a>
####mapView.halt()
Halts any pending transitions.

    * [mapView.halt()](#module_MapView^MapView#halt)

<a name="module_MapView^MapView#pointFromPosition"></a>
####mapView.pointFromPosition(position)
Get the position in pixels (relative to the left-top of the container) for the given geographical position.

**Params**

- position `LatLng` - in geographical coordinates.  

**Returns**: `Point` - Position in pixels, relative to the left-top of the mapView.  
    * [mapView.pointFromPosition(position)](#module_MapView^MapView#pointFromPosition)

<a name="module_MapView^MapView#positionFromPoint"></a>
####mapView.positionFromPoint(point)
Get the geographical coordinates for a given position in pixels (relative to the left-top of the container).

**Params**

- point `Point` - Position in pixels, relative to the left-top of the mapView.  

**Returns**: `LatLng` - Position in geographical coordinates.  
    * [mapView.positionFromPoint(point)](#module_MapView^MapView#positionFromPoint)

<a name="module_MapView^MapView#getSize"></a>
####mapView.getSize()
Get the size of the map-view in pixels.

**Returns**: `Array.Number` - Size of the mapView.  
    * [mapView.getSize()](#module_MapView^MapView#getSize)

<a name="module_MapView^MapView#getZoom"></a>
####mapView.getZoom()
Get the current zoom-level of the map, taking into account smooth transition between zoom-levels.
E.g., when zooming from zoom-level 4 to 5, this function returns an increasing value starting at 4 and ending
at 5, over time. The used zoomTransition can be set as an option.

**Returns**: `Number` - Zoom-level.  
    * [mapView.getZoom()](#module_MapView^MapView#getZoom)

<a name="module_MapView^MapView.DEFAULT_OPTIONS"></a>
####MapView.DEFAULT_OPTIONS
**Access**: protected  
    * [MapView.DEFAULT_OPTIONS](#module_MapView^MapView.DEFAULT_OPTIONS)
