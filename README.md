# KozakMaks-GTA5-Self-Driving-Car-CNN
# GTA5-Self-Driving-car

![Driving Unfamiliar Roads](Driving_Unfamiliar_roads.gif)

*Images are at 2x speed to show more driving in a shorter time span.*

## Inspiration

This project was inspired by [Sentdex/pygta5](https://github.com/Sentdex/pygta5).  
The aim was to create a slightly more realistic GTA5 self-driving car. By utilizing imitation learning, the model has learned to stay in lane and maintain its speed.

## The Model

*Drawing*

This model was trained using approximately 80,000 images with corresponding steering and throttle commands. The architecture was loosely modeled after [PilotNet by NVIDIA](https://arxiv.org/abs/1604.07316). However, the network was modified to add two regression heads—one for steering and one for throttle. Initially, the model was trained using only the steering command to learn robust convolutional features. Later, a second regression head was added and only the remaining regression layers were trained to complete the full model.

## Datasets

Two separate datasets were used for steering and throttle because the distribution for each heavily favored certain positions. The data was pruned to create a flatter distribution, preventing the model from overfitting. When one dataset had a balanced distribution, the other did not, hence the separate processing.

**Steering Dataset**  
_Before:_ ![Steering Before](path/to/steering_before.png)  
_After:_ ![Steering After](path/to/steering_after.png)

**Throttle Dataset**  
_Before:_ ![Throttle Before](path/to/throttle_before.png)  
_After:_ ![Throttle After](path/to/throttle_after.png)

## Prerequisites

- **GTA5 + Mods**
  - Script Hook V
  - Native Trainer
  - Enhanced Native Trainer
  - GTA V Fov v1.35
  - Extended Camera Settings
  - Hood Camera
  - Singleplayer Reveal Map
  - LeFix Speedometer 1.3.5 (**Important**)
- **Software & Libraries**
  - Python 3.6
  - OpenCV
  - Numpy
  - Tensorflow GPU
  - Keras
  - [x360ce](https://www.x360ce.com/)
  - [vJoy](http://vjoystick.sourceforge.net/site/)

## Usage

*Recommended to use dual monitors.*

1. **Download Model Weights:**  
   Download the model weights from [Google Drive](https://drive.google.com/open?id=1NgaGZ-oFjvl-GxJvOtqXdIedrumV64-o) and place them in the same directory as `GTA_SelfDrivingCar.py`.

2. **Launch GTA5:**  
   Run GTA5 in windowed mode at a resolution of 1280x720.

3. **Prepare the Environment:**  
   Find a car and enable the Hood Camera (press `8`).

4. **Run the Self-Driving Script:**  
   Execute the following command:
   ```bash
   python GTA_Self_Driving_Car.py
5.**CNN**
![SelfDrivingModel](https://github.com/user-attachments/assets/c677a5a4-0504-4faa-90f0-d3ee42a5a23c)
