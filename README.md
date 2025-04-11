# Ain-AlMaidan
# Ain AlMaidan – Smart Stadium Behavior Detection System

Ain AlMaidan is an AI-powered system that uses computer vision to detect violent or disruptive behavior in stadiums, such as fights, pitch invasions, or the use of fireworks. The system analyzes video footage in real time and alerts authorities for quick intervention, enhancing audience safety and event management.

### Project Goal
To create a real-time violence detection model for stadiums that helps:
- Improve safety and crowd control
- Enhance the experience of fans
- Support Saudi Vision 2030 by applying smart technologies in sports facilities

## Dataset
- Source: [Hockey Fight Dataset - Kaggle](https://www.kaggle.com/datasets/laertelag/hockey-fights)
- 40 videos for each class: "Fight" and "Non-Fight"
- Each video was processed to extract 30 grayscale frames (64x64 pixels)
- Video labels were inferred from filenames (e.g., fi*.avi = Fight)

## Data Preprocessing
- Converted frames to grayscale
- Normalized pixel values to range [0, 1]
- Ensured uniform frame size (64x64)
- Filtered out videos with less than 30 valid frames
- Split data into 80% training and 20% testing

## Model Architecture
The model uses a ConvLSTM2D architecture that combines the strengths of:
- CNN (Convolutional Neural Networks): for extracting spatial features from each frame
- LSTM (Long Short-Term Memory): for understanding the sequence of frames over time

### Layers:
- ConvLSTM2D layer with 24 filters
- Batch Normalization
- Flatten layer
- Dense layer with 64 units and ReLU
- Dropout (0.3)
- Output Dense layer with sigmoid activation (binary classification)

## Results
- Achieved 81% accuracy on the test set
- Model was saved in .h5 format for later use with real-time video input

## Future Work
- Expand dataset with real-life violence datasets: [Real-life Violence Situations](https://www.kaggle.com/datasets/mohamedmustafa/real-life-violence-situations-dataset)
- Use Transfer Learning and Data Augmentation for higher accuracy
- Integrate the system with live stadium surveillance feeds
