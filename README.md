# Autonomous car simulation
Used behavioral cloning to mimic the self driving car functionality in a simulated environment
## Dependencies

You can install all dependencies by running one of the following commands

```python
# Use TensorFlow without GPU
conda env create -f environments.yml 

# Use TensorFlow with GPU
conda env create -f environment-gpu.yml
```

Or you can manually install the required libraries (see the contents of the environemnt*.yml files) using pip.

## Data Generation
records images from center, left, and right cameras w/ associated steering angle, speed, throttle and brake using keyboard/joystick.
saves to CSV

### To train the model
Used a 9 layer convolutional network, based off of Nvidia's end-to-end learning for self driving car paper. 72 hours of driving data was collected in all sorts of conditions from human drivers

You'll need the data folder which contains the training images.

```python
python model.py
```

This will generate a file `model-<epoch>.h5` whenever the performance in the epoch is better than the previous best.  For example, the first epoch will generate a file called `model-000.h5`.

## Testing mode
We will just run autonomous mode, then run our model and the car will start driving



