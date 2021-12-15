# Machine-Learning-for-Video-Super-resolution
[Real-Time Single Image and Video Super-Resolution Using an Efficient Sub-Pixel Convolutional Neural Network](https://arxiv.org/abs/1609.05158) 
implementated by pytorch

## Requires:
- conda
- python 3.6.5
- Pytorch
- opencv

## Dataset
[VOC2012](https://pjreddie.com/projects/pascal-voc-dataset-mirror/) images for training and validation.
SET 5 |SET 14 | BSD 100 | Urban100 images for testing.
testing videos get from [youtube](https://www.youtube.com/watch?v=_VxLOj3TB5k).

## Methods
### Preprocessing
Generate the train and validation data by specific upscaling factors.
```
python data_utils.py --upscale_factor 2/3/4/8
```
### Training
```
python train.py --upscale_factor 2 --num_epochs 100
```
### Testing
image
```
python test_image.py --upscale_factor 2 --model_name epoch_2_100.pt
```
video
```
python test_video.py --upscale_factor 2 --model_name epoch_2_100.pt
```

### Results
|        | P     | S     | N     | R     |   | S      | S      | I      | M      |
|--------|-------|-------|-------|-------|---|--------|--------|--------|--------|
|        | 2×    | 3×    | 4×    | 8×    |   | 2×     | 3×     | 4×     | 8×     |
| video1 | 28.11 | 26.72 | 23.08 | 18.14 |   | 0.8512 | 0.7746 | 0.7023 | 0.6211 |
| video2 | 33.63 | 27.91 | 25.48 | 21.97 |   | 0.9023 | 0.7814 | 0.7524 | 0.6847 |
| video3 | 29.43 | 26.65 | 23.12 | 20.06 |   | 0.8848 | 0.7714 | 0.7321 | 0.6592 |

video1 SRF-2
![video1](results/SRF_2/video1.gif)

video2 SRF-4
![video1](results/SRF_4/video2.gif)

video3 SRF-8
![video1](results/SRF_8/video3.gif)
