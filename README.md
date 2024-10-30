# Waterloo-Point-Cloud-Database-4.0
This database was created by Su Honglei ([suhonglei@qdu.edu.cn](mailto:suhonglei@qdu.edu.cn)) and Lv Jianyu (lvjianyu@qdu.edu.cn) from Qingdao University in 2024. You are welcome to test it and make suggestions for modification. If you use our database [WPC4.0](https://drive.google.com/drive/folders/1nyRv0a76rVE7trPLHYVzOZzHG37nsth5?usp=sharing) in your paper (Google account required), please cite our paper:

@article{lv2024no,
  title={No-reference Bitstream-based Perceptual Quality Assessment of Octree-Lifting Encoded 3D Point Clouds},
  author={Lv, Jianyu and Su, Honglei and Liu, Qi and Yuan, Hui},
  journal={IEEE Transactions on Visualization and Computer Graphics},
  year={2024},
  publisher={IEEE}
}

The WPC4.0 database is composed of 168 Octree-Lifting encoded point clouds and corresponding bitstreams whose 14 original point clouds (Bag, Cake, Cauliflower, Glasses_case, Honeydew_melon, House, Litchi, Mushroom, Pen_container, Pineapple, Ping-pong_bat, Pumpkin, Statue, Tool_box) are from the [WPC database](https://github.com/qdushl/Waterloo-Point-Cloud-Database). Each original point cloud is encoded by 3 geometry parameters GQP{0.5, 0.25, 0.125} and 4 texture parameters TQP{28, 34, 40, 46} to produce 12 distortion levels. The rest of the encoding parameters are set with default values. The subjective test settings and raw data processing are the same as those in the WPC database.<br/><br/>

# streamPCQ-OL model

In order to extract the parameters of the streamPCQ-OL model from the bitstream of the distorted point cloud, we use MPEG's G-PCC[mpeg-pcc-tmc13-release-v20.0](https://github.com/MPEGGroup/mpeg-pcc-tmc13/releases/tag/release-v20.0) to extract the parameters GQP and TQP. Get the Y-std from the decoded point cloud and then use the extracted parameters for perceptual quality prediction.

If you have any specific questions about streamPCQ-OL, please feel free to ask.

In addition, we saved the prediction scores of streamPCQ-OL on the WPC4.0 database into streamPCQ_OL_WPC4.xlsx for subsequent research.

## Run

Put tmc3.exe, decoder.cfg, savePointCloudData.m, calculateStd.m, streamPCQ_OL_model.m, streamPCQ_OL.m in the demo and the point cloud code stream files that need perceptual quality evaluation in the same working directory, and run streamPCQ_OL.m to perform perceptual quality evaluation of all point cloud code stream files in the current working directory, and the evaluation results will be saved in streamPCQ_OL.xlsx.

###Demo

We provide the corresponding streamPCQ-OL_demo files. Running the streamPCQ_OL.m file in the demo folder can perform perceptual quality prediction for all point cloud code stream files in the current folder, and the prediction results are saved in the streamPCQ_OL.xlsx file.

***-----------COPYRIGHT NOTICE STARTS WITH THIS LINE------------***
***Copyright (c) 2024 The Qingdao University All rights reserved.***

Permission is hereby granted, without written agreement and without license or royalty fees, to use, copy, modify, and distribute this database (the point clouds, the results and the source files) and its documentation for any purpose, provided that the copyright notice in its entirety appear in all copies of this database, and the original source of this database, Intelligent Multimedia Signal Processing (IMSP) Laboratory at Qingdao University, is acknowledged in any publication that reports research using this database.

***Additional Restrictions for streamPCQ-OL Model:***

The streamPCQ-OL model is intended for non-commercial academic research use only. Any use of the streamPCQ-OL model for commercial purposes is strictly prohibited without the prior written consent of The Qingdao University. Redistribution or modification of the streamPCQ-OL model for commercial gain is not allowed.

***-----------COPYRIGHT NOTICE ENDS WITH THIS LINE------------***

# Acknowledgment

This project is based on [G-PCC](https://www.mpeg.org/standards/MPEG-I/9/) of [MPEG](https://www.mpeg.org), thanks for their excellent works.
