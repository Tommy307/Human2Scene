# Human2Scene
## Synthesis of Indoor Scene Point Cloud Dataset Featuring Clothed Human Bodies
<div align="center">
<a href="https://aycatakmaz.github.io/">Lang Zhou</a><sup>1</sup>,
<a href="https://jonasschult.github.io/">Haolin Xie</a><sup>1</sup>,
<a href="https://ikaftan.github.io/">Zedan Zheng</a><sup>1</sup>,
<a href="https://cmakcay.github.io/">Fan Zhou</a><sup>1</sup>,
<a href="https://www.vision.rwth-aachen.de/person/1/">Zhuo Su</a><sup>1</sup>

<sup>1</sup>the School of Computer Science and Engineering, National Engineering Research Center of Digital Life, Sun Yat-sen University, China

</div>
<br><br>

We propose the first indoor scene point cloud dataset featuring clothed human called Human2Scene, that directly positions clothed human models into existing point cloud dataset. In an extensive analysis, we validate the benefits of training on synthetic data on multiple point cloud segmentation baselines and tasks. 

Here are some examples of our synthetic point clouda dataset:

![Examples of the synthetic data](./img/dataset_example_images_00.png)

Existing synthesis methods primarily aim to make the human models in the synthetic data appear more visually natural. 

In contrast, our work focuses on a different goal: **we aim to increase the complexity and diversity of the synthetic data**. This is intended to enhance the generalization performance of scene point cloud semantic and instance segmentation models trained on the synthetic dataset.

## Data download
The dataset could be downloaded through Baidu Netdisk [https://pan.baidu.com/s/1_aFk1AaO1YIbBiKhskfq6w?pwd=rac2](https://pan.baidu.com/s/1_aFk1AaO1YIbBiKhskfq6w?pwd=rac2).

## Data structure
We have applied our synthetic method to the large indoor scene point cloud dataset ScanNet, and arranged the result follow the data structure of ScanNet. 

While the data group of training and validation are made from ScanNet, the test data is seeking more intricate data source. As a matter of that, we chose LiDAR-Net to generate synthetic point clouds for test.

```
├── Human2Scene
│   ├── train <- the training data
│   │   ├── scene0000_00_vh_clean_2.ply 		 					  <- point cloud data
│   │   ├── scene0000_00_vh_clean_2.0.010000.segs.json  <- instance segmentation indices
│   │   ├── scene0000_00.aggregation.json 							<- instance segmentation aggregation annotations
|   |   |── scene0000_00_vh_clean_2.labels.ply 				  <- semantic segmentation annotations
│   │   └── ...
│   ├── val <- the validation data
│   └── test <- the test data

```

# TODO
- Add point cloud semantic & instance segmentation code base to the repository.
- Provide pretrained segmentation models analysed in the experiment part.

# Acknowledgements

This repository is based on the [ScanNet](https://github.com/ScanNet/ScanNet) and [LiDAR-Net](http://lidar-net.njumeta.com) dataset.
