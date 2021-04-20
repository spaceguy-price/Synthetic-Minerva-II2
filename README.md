## Synthetic-Minerva-II2
Contains the synthetic dataset developed for our CVPR2021 paper.

:rocket: A Monocular Pose Estimation Case Study: The Hayabusa2 Minerva-II2 Deployment.

Images shared under CC0.

***Synthetic*** Minerva-II2 images currently available for download at:
[Price's Google Drive](https://drive.google.com/drive/folders/1ZhmzKEgsCmU2jB3aZuLk97uaa4_9o4dP?usp=sharing)

The ***real*** Minerva-II2 images are copyright to the Hayabusa 2 Optical Navigation Camera (ONC) system team: JAXA, Chiba Institute of Technology, University of Tokyo, Kochi University, Rikkyo University, Nagoya University, University of Aizu and AIST. For access to the real Minerva-II2 deployment images permission will need to be obtained from JAXA. 

For any questions or difficulties regarding accessing the dataset, please feel free to contact the authors. 
pricea@dc.tohoku.ac.jp

### Annotation File Format
Three annotation files are shared. Their content format is identical.
1. SetA
2. SetB
3. Tumble

The annotation files are formatted with the following members:
- "image": "image_#.png"
- "joints": [[x1,y1],[x2,y2],...[x16,y16]]    [pixels]
- "pose": [q0, q1, q2, q3, x, y, z]           [quaternion|metres]
Example entry:
'{"image":"image_1.png","joints":[[1,1],[2,2],[3,3],[4,4],[5,5],[6,6],[7,7],[8,8],[9,9],[10,10],[11,11],[12,12],[13,13],[14,14],[15,15],[16,16]],"pose":[1,0,0,0,0,0,0.5]}'

The "joints" member contains 16 [x,y] pairs indicating the location of a vertice in the image.
The "pose" member is a 1x7 vector containing the camera frame pose of the Minerva-II2 (quaternion|cartesian vector).

If desired, one can generate their own "joints" annotations for training based on the pose. We include the joints information here for convenience. Please note, the datasets have a slight distinction:
- The SetA   "pose" [cartesian] vector points to the [0.875, -0.04, 4.76]_MinervaII2_bodyFrame
- The SetB   "pose" [cartesian] vector points to the [0, 0, 0]_MinervaII2_bodyFrame
- The Tumble "pose" [cartesian] vector points to the [0, 0, 0]_MinervaII2_bodyFrame

### Minerva-II2 vertices
The geometry of the Minerva-II2 vertices are shared in MinervaII2_Vertices.txt. The values are in [mm].

### Virtual Camera Rendering Parameters
The renderings were designed to match the Hayabusa2 ONC-W2 camera parameters.
- resolution:    1024x1024
- sensor size:   13um x 13um
- focal length:  10.38 mm
- field of view: 68.89 deg
