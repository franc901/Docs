---
title: "loadCollectionGraph"
_old_id: "1193"
_old_uri: "2.x/class-reference/xpdoobject/static-object-loaders/loadcollectiongraph"
---

## xPDOObject::loadCollectionGraph()

This function is responsible for loading a collection of object instances, as well as related object instances specified in a class "graph", from the tables represented by a specific set of related classes.

## Syntax

API Docs: <http://api.modxcms.com/xpdo/om/xPDOObject.html#loadCollectionGraph>

``` php 
function loadCollectionGraph(& $xpdo, $className, $graph, $criteria, $cacheFlag)
```