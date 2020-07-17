
# prior-map-server

## 1. Introduction

Prior map server provides basic APIs for both *Radar Prior Map* and *Lidar Prior Map*. 

## 2. Getting Started

Prior map server can be easily installed using tapkg
```
tspkg install prior_map_server
```

## 3. Usage

### 3.1. Radar Prior Map

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
	:param vehicle_loc: ndarray with shape (3,) or (6,)
	"""
```
As the map is consisted of multiple sub-maps, you will need to let the server know your location before utilize the prior map. And `vehicle_loc` could be the location of base point of imu0 under **ENU** coordinate or direct gpsimu valus of Novatel sensor output.

```python
def match_point_cloud(self, pts, cov_vec=None):
	"""
	Match realtime radar point cloud input with radar prior map.
	:param pts: ndarray with shape (n, 3) or (n, 2) under ENU coordinate
	:param cov_vec: none or ndarray indicate covariance vectors
	:return: ndarray with shape (n, 2) indicate occupancy probablities 
	"""
```
Please remember all the input points and vectors should be under **ENU** coordinate. The param `pts` indicates radar point cloud, which cloud be of shape (n, 3) or (n, 2) as the last column could be omitted. The param `cov_vec` indicates distribution range of each point. As we assume the distribution of each point is a 2D Gaussian, the covariance vectors can be represented as a ndarray with shape (n, 6) or (n, 4) as the last column clould also be omitted.

The return values are represents as a ndarray with shape (n, 2), where the first column is the low layer occupancy probabilities while the second column represents the top layer.

```python
def visualize_map(self):  
	"""  
	Visualize nearby radar prior map
	"""
```
Function for visualize nearbe radar prior map

```python
def visualize(self, pts, probs):  
	"""  
	Function to visualize the point cloud & probablities 
	:param pts: radar point cloud 
	:param probs: (n, 2) ndarray indicate low & high layer occupancy probablities 
	"""
```
Function for visualize radar point cloud and corresponding low & high layer occupancy probablities.


### 3.2. Lidar Prior Map

For getting start, you should create a lidar prior map server instance as following
```python
from prior_map_server import LidarPriorMapServer
map_server = LidarPriorMapServer('path/to/lidar/prior/map')
```

```python
def update_vehicle_loc(self, vehicle_loc):  
```
```python
def match_point_cloud(self, pts):  
```

```python
def visualize_point_cloud(pts, info, vis_range=80., downsample_n=2):
```
<!--stackedit_data:
eyJoaXN0b3J5IjpbLTI1NTUzMTMyNywtMTQyNzU4MjUyNV19
-->