# Deflecting Adversarial Attacks with Pixel Deflection


Code: https://github.com/tanmayiitj/DAI-Project

Google Colab: Provide google colab for easier understanding

Requirements:

1. Keras 2.0+
2. Scipy 1.0+  (Older version of scipy wavelet transform does not have BayesShrink)

## Example


```python
» python main.py                                                                                                  02:24:51 on 2023-05-10
Image: images/n02447366_00008562.png, True Class: 'badger'
Before Defense :
Predicted Class  skunk:0.59 , badger:0.15 , polecat:0.07 , wood_rabbit:0.02 , weasel:0.01
After Defense :
Predicted Class  badger:0.90 , skunk:0.08 , polecat:0.01 , weasel:0.00 , mink:0.00
```
---------------------------------------------------------------------

```
» python main.py -process_batch -directory ./images

After recovery Top 1 accuracy is 66.67 and Top 5 accuracy is 100.0

```
---------------------------------------------------------------------



## Usage

### Single image

```python
» python main.py -image <image_path> -map <map_path>
```


### Batch usage

```python
» python main.py -process_batch -directory <directory_containing_images>
```


In batch usage the map file is expected to have same name as image file but inside './maps' directory.

### Without map
To use without a map, pass in '-disable_map' argument, e.g:

```python
» python main.py -disable_map                                                                                     02:26:02 on 2018-02-01
Image: images/n02447366_00008562.png, True Class: 'badger'
Before Defense :
Predicted Class  skunk:0.59 , badger:0.15 , polecat:0.07 , wood_rabbit:0.02 , weasel:0.01
After Defense :
Predicted Class  badger:0.88 , skunk:0.11 , polecat:0.01 , weasel:0.00 , mink:0.00
```


### Detailed usage

```
» python main.py --help
  -h, --help            show this help message and exit
  -image
  -map 
  -directory
  -process_batch
  -disable_map
  -classifier 
    options: resnet50, inception_v3, vgg19, xception
  -denoiser 
    options: wavelet, TVM, bilateral, deconv, NLM
  -batch_size 
  -sigma 
  -window 
  -deflections 
```  

