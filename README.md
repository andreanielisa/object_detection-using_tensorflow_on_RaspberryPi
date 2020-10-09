# object_detection-using_tensorflow_on_RaspberryPi

## Prerequisites

Clone the repo and rename it tensorflow.

Create a virtual environment
```sh
python3 -m venv tensorflow
```
and activate the environment
```sh
source tensorflow/bin/activate
```

install all the prerequisites with:
```sh
bash get-prequisites.sh
```
(to install  OpenCV, TensorFlow 2.2.0, and matplotlib)

and
```sh
source ./install-object-detection-api.sh
```
(clones the tensorflow/models repo, compiles the protos, and installs the Object Detection API through an Environment Variable)

## Run the model

Each time you open a new terminal reactivate the object_detection module with:
```
export PYTHONPATH=$PYTHONPATH:/home/pi/tensorflow/models/research:/home/pi/tensorflow/models/research/slim

```
Download a model from the Tensorflow 2 model zoo and create (or download) a .pbtxt file for the labels
Place both the directory containing the model and the labelmap file inside od-models, 
then you can use the command

```sh
python TF-PiCamera-OD.py --model od-models --labels od-models/labelmap.pbtxt
```

to run the model on your Raspberry pi.
