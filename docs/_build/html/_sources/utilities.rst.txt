.. _utilities:


***************************************
Utilities
***************************************

I/O: File
=============================
utils_io_file.py is a light-weight python library dealing with I/O that is related to files.

Its functionalities include::

- validate file format
- find file extensions
- find out whether a file is an image
- find out whether a file is a video
- read image via opencv wrapper
- read video via opencv wrapper

TODO: ADD PILLOW WRAPPER FOR FILE I/O

Please kindly contribute your functions if you have more. 

The code is open-sourced in SVAI group. Please log in your Gitlab to 
access the code.  
Link: `Script <http://bit.jd.com/svai/openSVAI/blob/dev/utility/utils_io_file.py>`_


I/O: Folder
=============================
utils_io_folder.py is a light-weight python library dealing with I/O that is related to folders.

Its functionalities include::

- get immediate sub-folder names/paths
- get immediate childfile names/paths
- create folder if it does not exist
- get folder name from path

Please kindly contribute your functions if you have more. 

The code is open-sourced in SVAI group. Please log in your Gitlab to 
access the code.  
Link: `Script <http://bit.jd.com/svai/openSVAI/blob/dev/utility/utils_io_file.py>`_

The project is currently in rapid development.
For now, please follow the instructions in the comment section, or run the bash script for your convenience.


Pose: 3d-nms
=============================
utils_nms.py implements the cross-heatmap non-maximum suppression for human pose estimation.

This post processing procedure improves upon the raw performance of human pose estimation (HPE), regardless of the HPE approach.

The code is open-sourced in SVAI group. Please log in your Gitlab to 
access the code.  
Link: `Script <http://bit.jd.com/svai/openSVAI/blob/dev/utility/utils_nms.py>`_

The project is currently in rapid development.
For now, please follow the instructions in the comment section, or run the bash script for your convenience.


Pose: common
=============================
utils_pose.py implements common utility routines for human pose estimation.

Its functionalities include::

- Pre-processing images: (1) normalize RGB image; (2) convert a list of images into network input blob; 
- Data augmentation for human pose estiamtion: (1) scaling; (2) flipping; (3) padding 
- Visualization for human pose estimation: (1) heatmaps; (2) joints and keypoints
- Post-processing images and heatmaps: (1) flip the order of heatmaps; (2) crop images; (3) overlay scaled image to a gray image with original image size 
- Saving pose predictions: (1) save heatmaps; (2) save keypoints

The code is open-sourced in SVAI group. Please log in your Gitlab to 
access the code.  
Link: `Script <http://bit.jd.com/svai/openSVAI/blob/dev/utility/utils_pose.py>`_

The project is currently in rapid development.
For now, please follow the instructions in the comment section, or run the bash script for your convenience.


Pose: heatmaps
=============================
utils_convert_heatmap.py implements heatmap-related routines for human pose estimation.

Its functionalities include::

- Conversion between keypoint coordinates and heatmaps
- Padding heatmaps
- Averaging multiple heatmap sets (each set is a whole list of heatmaps including all keypoint classes)

The code is open-sourced in SVAI group. Please log in your Gitlab to 
access the code.  
Link: `Script <http://bit.jd.com/svai/openSVAI/blob/dev/utility/utils_convert_heatmap.py>`_

The project is currently in rapid development.
For now, please follow the instructions in the comment section, or run the bash script for your convenience.


Pose: gen_hourglass
=============================
gen_hourglass.py implements the caffe version of the hourglass network for human pose estimation.

It is basically a python script that writes a prototxt file for the hourglass network. 
It could be conveniently modified for other network structures.

The code is open-sourced in SVAI group. Please log in your Gitlab to 
access the code.  
Link: `Script <http://bit.jd.com/svai/openSVAI/blob/dev/utility/gen_hourglass.py>`_

The project is currently in rapid development.
For now, please follow the instructions in the comment section, or run the bash script for your convenience.



Pose: gen_fractal
=============================
gen_fractal.py implements the caffe version of the fractal network for human pose estimation.

It is basically a python script that writes a prototxt file for the fractal network. 
It could be conveniently modified for other network structures.
The fractal network is a variation of the hourglass network in that it replaces the resnet module with the inception-resnet module.

The code is open-sourced in SVAI group. Please log in your Gitlab to 
access the code.  
Link: `Script <http://bit.jd.com/svai/openSVAI/blob/dev/utility/gen_fractal.py>`_

The project is currently in rapid development.
For now, please follow the instructions in the comment section, or run the bash script for your convenience.