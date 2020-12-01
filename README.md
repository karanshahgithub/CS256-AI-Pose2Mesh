CS256-AI-TeamC-3D Human Pose Estimation Project
Team project implementation of the state-of-the-art paper:

https://arxiv.org/pdf/2008.09047.pdf Pose2Mesh: Graph Convolutional Network for 3D Human Pose and Mesh Recovery from a 2D Human Pose, August 2020.

Project report: [add PDF copy]

Project presentation slides: [add PDF copy]

Implementation:

TeamC used the AWS EC2 p2.xlarge (original Pose2Mesh used Google TPUs)

Deep Learning AMI (Ubuntu 18.04) Version 34.0 AMI

4vCPUs

Downloading data:

Datasets for this project are very large. These are stored in Google drive. We have developed a mechanism using a third-party tool to create a bridge between our AWS EC2 instance and Google drive.

New data set: Web crawler []

Pose2Mesh training and testing:

***Sample training command:***
> python main/train.py --gpu 0 --cfg ./asset/yaml/pose2mesh_cocoJ_train_human36_coco_muco.yml

***Sample testing command:***
> python main/test.py --gpu 0 --cfg ./asset/yaml/pose2mesh_human36J_test_human36.yml

Here based on the selection of dataset, user can pass different config yaml file.

Posenet training took TeamC about 45 minutes per epoch for 40 epochs.

Pose2mesh training and testing:

The pose2mesh represents the meshnet part of the architecture and uses the previously trained posenet. Pose2mesh training took TeamC about 12 - 13 hours per epoch for 15 epochs.

Optimizer experiment:

The original research paper used RMSPROP while we selected Adam optimizer
