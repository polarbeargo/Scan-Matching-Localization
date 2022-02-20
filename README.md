# Scan-Matching-Localization  
## Project overview  
- In this final project our goal will be to localize a car driving in simulation for at least 170m from the starting position and never exceeding a distance pose error of 1.2m. The simulation car is equipped with a lidar, provided by the simulator at regular intervals are lidar scans. There is also a point cloud map map.pcd already available, and by using point registration matching between the map and scans localization for the car can be accomplished. This point cloud map has been extracted from the [CARLA simulator](https://carla.org/).  

## Project Steps

Step 1: Filter scan using voxel filter  
- The first step is fairly short - make use of `cloudFiltered` and `scanCloud` to filter the point cloud using a voxel grid.    

Step 2: Find pose transform by using ICP or NDT matching  
- The second step is the `main` portion of the exercise. By using ICP matching in order to find the pose transformation.  

Step 3: Transform the scan so it aligns with ego's actual pose and render that scan  
- Transform the filtered scan by using our calculated transform into a new point cloud using `pcl` and update what is fed into `renderPointCloud` to change `scanCloud` into newly transformed point cloud.  

## How to run this project
1. Compile the code (Terminal Tab 1)  
```
cd /home/workspace/c3-project

cmake .

make
```
2. Launch the simulator in a new terminal tab (Terminal Tab 2)
```
su - student

cd /home/workspace

./run-carla.sh
```
3. Run the project code back in the first tab (Terminal Tab 1)  
```
cd /home/workspace/

Using Normal Distributions Transform (NDT)
./cloud_loc 

Using Iterative Closest Point (ICP)
./cloud_loc 2
```
