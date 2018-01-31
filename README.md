# deeptracking

Torch + python implementation of [Deep 6-DOF Tracking](https://arxiv.org/abs/1703.09771)

Note that a docker file is available

The code to parse a ply file is not provided, this framework needs an implementation of [plyparser.py](https://github.com/lvsn/deeptracking/blob/develop/deeptracking/utils/plyparser.py)


TODO: update with the more recent pytorch framework...

The datasets and 3D models from the paper can be found [Here](http://vision.gel.ulaval.ca/~jflalonde/projects/deepTracking/index.html).

### Dependences installation
Please refer the odt files for more details about this project (installation ,dataset ,file change etc.)
There should have everything you need for the project including setup the environment , make up json , download dataset and some issues you might meet 
when running the project(there should be a plyparser issue in my develop repo which is what I am dealing with it.Just as a suggestion ,you might need
try some different version and diffrent installation ways of plyfile to have a test of it .Making plyparser work is just important than everything as 
other thing I have shared the details.Tested in ubuntu14.4.5,python3.4 as default.)BTW,you can also refer the wiki to install everything and have a glance of the whole project:https://github.com/Myzhencai/deeptracking/wiki

### Warnings
This project use python3 and Gpu with cuda cause there have the cnn etc.And I just installed the pytorch from source after I installed 
Hugh Perkins's [pytorch](https://github.com/hughperkins/pytorch),I do not know if it is neccessary so I did not mention it in the details_of_project
folder.

## Generating data
### Generating synthetic data
Run:
```bash
python generate_synthetic_data.py config_file.json
```

#### dependencies
- cv2
- tqdm
- pyOpenGL
- glfw
- numpngw

#### configuration
see this [example file](https://github.com/lvsn/deeptracking/blob/develop/configs/generate_synthetic_example.json)

### Generating real data
Run:
```bash
python generate_real_data.py config_file.json
```

#### dependencies
- cv2
- tqdm
- pyOpenGL
- glfw
- numpngw

#### configuration
see this [example file](https://github.com/lvsn/deeptracking/blob/develop/configs/generate_real_example.json)

## Train
Run:
```bash
python train.py config_file.json
```

#### dependencies
- Hugh Perkins's [pytorch](https://github.com/hughperkins/pytorch)
- scipy, skimage, numpy
- tqdm
- numpngw
- slackclient (could be removed)

#### configuration
see this [example file](https://github.com/lvsn/deeptracking/blob/develop/configs/train_example.json)

## Test
#### Sensor
Will run the tracker with a sensor (kinect 2)
```bash
python test_sensor.py config_file.json
```

#### Sequence
Will run the tracker on a sequence (folder) and save the error in a file
```bash
python test_sequence.py config_file.json
```

#### dependencies
- cv2
- Hugh Perkins's [pytorch](https://github.com/hughperkins/pytorch)
- pyOpenGL
- glfw
- numpngw
- [pyfreenect2](https://github.com/MathGaron/py3freenect2) (for Kinect2 sensor)

#### configuration
see this [example file](https://github.com/lvsn/deeptracking/blob/develop/configs/test_example.json)
