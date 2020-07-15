# prior-map-server

## 1. Introduction

Prior map server provides basic APIs for both *Radar Prior Map* and *Lidar Prior Map*. 

## 2.Getting Started

Prior map server can be easily installed using tapkg
```
tspkg install prior_map_server
```

## Usage

### Radar Prior Map

Radar prior map is in the form of 2D occupancy grid which each grid records the probability of that grid being occupied by a static object. 

For radar prior map users, you can import the corresponding prior map server as following example.
```python3
from prior_map_server import RadarPriorMapServer

# To create a server instance
map_path = '/path/to/map/folder'
map_server = RadarPriorMapServer(map_path)
```
As the 


### Lidar Prior Map

<!--stackedit_data:
eyJoaXN0b3J5IjpbNTUxNDQ1NjIwXX0=
-->