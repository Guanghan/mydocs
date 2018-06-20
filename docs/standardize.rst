.. _standardize:


***************************************
Standardization
***************************************

The standardization of output format from each module. It is essential for end-to-end training and testing that employ different modules, 
including but not limited to candidate detection, human pose estimation, portrait segmentation (or human parsing), candidate tracking and pose tracking.

Provided various end-to-end module baselines for common tasks, the standardizing of end-to-end module outputs ensure that 
(1) different methods may co-exist in each module; 
(2) these modules are able to run end-to-end;

Once the standardization is fully implemented, we can start implementing a centralized program that calls different modules based on a configuration file, 
the modules of which can be from different deep learning frameworks. 

The common formats for object detection, segmentation, multi-person human pose estimation and tracking include: (1) COCO format, (2) PoseTrack format, and (3) OpenPose format.
COCO and PoseTrack are the most influential benchmarks for object detection/segmentation and pose tracking, respectively.
These two formats are the official formats defined by the dataset authors. 

The OpenPose format, on the other hand, is a ever-changing output format from the open-sourced project named "OpenPose". 
It is the first real-time multi-person human pose estimation project that is available to the public. Therefore, it is widely adopted by researchers and engineers. 
It is not the most accurate algorithm at the moment, but it is very fast.
Many methods may improve upon this open-source code, and output their results in the same format. 
So we implement the conversion of this OpenPose format as well.


Format Examples
=============================
Multiple examples are provided. They are json format files, illustrating the format of results from (1) COCO, (2) PoseTrack, (3) OpenPose.
We also provide the standard format we propose to use in our openSVAI project. 

The code is open-sourced in SVAI group. Please log in your Gitlab to 
access the code.  

Link: `Examples: COCO <http://bit.jd.com/svai/openSVAI/blob/dev/standardize/examples/COCO.json.example>`_

Link: `Examples: PoseTrack <http://bit.jd.com/svai/openSVAI/blob/dev/standardize/examples/posetrack.json.example>`_

Link: `Examples: OpenPose <http://bit.jd.com/svai/openSVAI/blob/dev/standardize/examples/openpose.json.example>`_

Link: `Examples: Standard <http://bit.jd.com/svai/openSVAI/blob/dev/standardize/examples/standard.json.example>`_


Output Detections To SVAI Standard Json
========================================
We provide the example code to convert detection results into SVAI standard json output.
The detections can be organized in any form. Usually the detections results are numpy array or python's native data format.
We can use the tools provided in our library to conveniently convert the results into json string, and/or write to file.

The code is open-sourced in SVAI group. Please log in your Gitlab to access the code.  

Example Code: `Examples: detections to json <http://bit.jd.com/svai/openSVAI/blob/dev/standardize/convert/detect_to_standard/detect_to_standard.py>`_


We also provide specific code to output detection results from Deformable ConvNets in our SVAI format.

The code is open-sourced in SVAI group. Please log in your Gitlab to access the code. 

Example Code: `Examples: RFCN to standard json <http://bit.jd.com/svai/openSVAI/blob/dev/standardize/convert/detect_to_standard/RFCN.py>`_


Read Detections From SVAI Standard Json
========================================
We provide the example code to load detection results of SVAI standard json format into python native format, for further processing (e.g., in the human pose estimation phase).

We also give a specific example of converting the SVAI standard json format into Cascaded Pyramid Networks (CPN) format. With the provided utility code, the conversion is very convenient.  

The code is open-sourced in SVAI group. Please log in your Gitlab to access the code.  

Example Code: `Examples: read standard json <http://bit.jd.com/svai/openSVAI/blob/dev/standardize/convert/keypoint_to_standard/read_standard_detect.py>`_


Output Keypoints To SVAI Standard Json
========================================
We provide the example code to convert keypoint results into SVAI standard json output.
The keypoints can be organized in any form. Usually the keypoints results are numpy array or python's native data format.
We can use the tools provided in our library to conveniently convert the results into json string, and/or write to file.

The code is open-sourced in SVAI group. Please log in your Gitlab to access the code.  

Example Code: `Examples: keypoints to json <http://bit.jd.com/svai/openSVAI/blob/dev/standardize/convert/keypoint_to_standard/keypoint_to_standard.py>`_

We provide specific code to output human keypoint results from Cascaded Pyramid Networks (CPN) in our SVAI format.

Example Code: `Examples: CPN to standard json <http://bit.jd.com/svai/openSVAI/blob/dev/standardize/convert/keypoint_to_standard/CPN.py>`_


Visualizer
============
We provide code to visualize detection as well as human pose estimation results based on the openSVAI's standard json output.

The detection results is given with a bounding box, giving the object class name and its confidence.

The human pose estimation results include two parts: (1) the keypoints of each detected human candidate, (2) the keypoint associations to form body and limbs.
This can be easily customized.

The code is open-sourced in SVAI group. Please log in your Gitlab to access the code.  

Code: `Keypoint Visualizer <http://bit.jd.com/svai/openSVAI/blob/dev/standardize/convert/keypoint_to_standard/keypoint_visualizer.py>`_

Code: `Detection Visualizer <http://bit.jd.com/svai/openSVAI/blob/dev/standardize/convert/detect_to_standard/detection_visualizer.py>`_

Code: `Overall Visualizer <http://bit.jd.com/svai/openSVAI/blob/dev/standardize/convert/keypoint_to_standard/visualizer.py>`_


Conversion Between Formats
=============================
We provide a series of utilities to convert between different formats.
Currently we provide these conversions:

 - OpenPose format to PoseTrack format
 - OpenPose format to COCO format

TODO: convert between standard format and all the other formats

The code is open-sourced in SVAI group. Please log in your Gitlab to 
access the code.  

Link: `OpenPose to COCO <http://bit.jd.com/svai/openSVAI/blob/dev/standardize/convert/openpose_to_COCO>`_

Link: `OpenPose to PoseTrack <http://bit.jd.com/svai/openSVAI/blob/dev/standardize/convert/openpose_to_poseTrack>`_


Other Scripts: Batch Testing
=============================
We provide bash scripts for batch testing.
Currently we provide the batching test of multi-person human pose estimation for PoseTrack challenge, based on OpenPose and its descendent algorithms.

TODO: add human parsing batch testing scripts based on deeplabv3+.

The code is open-sourced in SVAI group. Please log in your Gitlab to 
access the code.  

Link: `Scripts <http://bit.jd.com/svai/openSVAI/blob/dev/standardize/scripts>`_
