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
```python
from prior_map_server import RadarPriorMapServer

# To create a server instance
map_path = '/path/to/map/folder'
map_server = RadarPriorMapServer(map_path)
```

**Server APIs**
```python
def update_vehicle_loc(self, vehicle_loc):
	"""
	Update vehicle location & cached submaps
	:vehicle_loc: ndarray with shape (3,) or (6,)
	"""
```
As the map is consisted of multiple sub-maps, you will need to let the server know your location before utilize the prior map. And `vehicle_loc` should be gpsimu valus of Novatel sensor ou

```python
```



### Lidar Prior Map

<!--stackedit_data:
eyJoaXN0b3J5IjpbLTIxMDA1MzY0MzJdfQ==
-->