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
For radar prior map users, you can import the corresponding prior map server as following example.
```python3
from prior_map_server import RadarPriorMapServer

# To create a server instance
map_path = '/'
map_server = RadarPriorMapServer(map_path)
```
Where `map_path` is the path to 

### Lidar Prior Map

<!--stackedit_data:
eyJoaXN0b3J5IjpbNjgzMDE0NTg2XX0=
-->