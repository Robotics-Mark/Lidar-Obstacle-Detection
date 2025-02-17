# Lidar-Obstacle-Detection

Lidar obstacle detection using PCL and C++
  
See the [demo on YouTube](https://youtu.be/vvIn1Js49oA)

[image1]: ./docs/images/step-0-original.png
[image2]: ./docs/images/step-1-filter.png
[image3]: ./docs/images/step-2-segmentation.png
[image4]: ./docs/images/step-3-clustering.png
[image5]: ./docs/images/step-4-bboxes.png
[gif1]: ./docs/images/detection-result.gif

## Approach

This project is aimed to show basic scenarios for processing point clouds to detect the obstacles, 
and use it to detect cars and trucks on a narrow street using Lidar data.

### The detection pipeline includes the following steps:

**Step 1:** Load PCD data from file

![Load PCD][image1]

**Step 2:** Apply voxel grid filtering

![Filtering][image2]

**Step 3:** Segment the filtered cloud into two parts, road and obstacles

![Segmentation][image3]

**Step 4:** Cluster the obstacle cloud

![Clustering][image4]

**Step 5:** Render bounding boxes around the clusters

![BBoxes][image5]

The segmentation, and clustering methods were created from scratch.

The final result looks like the animation below:

![Final result][gif1]

## Installation
It requires pcl 1.9.1
So after pulling git you need 

``` git checkout pcl-1.9.1```
to point pcl installation to a specific directory 
```cmake -DCMAKE_INSTALL_PREFIX=/home/adminstator/MARK/pcl/install ..```

to make the lidar-detector code point to that specific PCL

``` cmake -DCMAKE_PREFIX_PATH=/home/adminstrator/MARK/pcl/install ..```

### Ubuntu 

```bash
$> sudo apt install libpcl-dev
$> cd ~
$> git clone https://github.com/olpotkin/Lidar-Obstacle-Detection.git
$> cd Lidar-Obstacle-Detection
$> mkdir build && cd build
$> cmake ..
$> make
$> ./environment
```

### Windows 

http://www.pointclouds.org/downloads/windows.html

### MAC

#### Install via Homebrew
1. install [homebrew](https://brew.sh/)
2. update homebrew 
	```bash
	$> brew update
	```
3. add  homebrew science [tap](https://docs.brew.sh/Taps) 
	```bash
	$> brew tap brewsci/science
	```
4. view pcl install options
	```bash
	$> brew options pcl
	```
5. install PCL 
	```bash
	$> brew install pcl
	```

Possible issue: 'simulation is required but glew was not found':
- check details [here](https://github.com/PointCloudLibrary/pcl/issues/2997#issuecomment-536234201)

#### Prebuilt Binaries via Universal Installer
http://www.pointclouds.org/downloads/macosx.html  
NOTE: very old version

#### Build from Source

[PCL Source Github](https://github.com/PointCloudLibrary/pcl)

[PCL Mac Compilation Docs](http://www.pointclouds.org/documentation/tutorials/compiling_pcl_macosx.php)
