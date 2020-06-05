# Deep Learning Exercise Repetitions Counter

**Disclaimer:** This project was developed to integrate with an Android application during a 24 hours hackathon. One of the key elements was to keep the model small, capable of performing well on phones and easy to train with data manually gathered during those 24 hours. Therefore, this a simplistic approach to the problem of counting push ups, pull ups and squats. 


## Goal

## Workflow 

- Gather videos from push ups 

- Use farneback optical flow algorithm to preprocess the videos frame by frame.

- Label individually a few hundred of images generated.

- Train a deep neural network using those images. 

- Develop a method to count the repetition from the analysis of the movement in the video.

- Process test videos using a pipeline composed of the farneback optical flow algorithm + the deep neural network + the algorithm to estimate the repetitions using the predictions of the network.

### Dataset construction 

### Model training 

### Counting repetitions

### Evaluation on a test video

[![Video1](https://img.youtube.com/vi/wf9ZE0j2Q_o/0.jpg)](https://www.youtube.com/watch?v=wf9ZE0j2Q_o "Video 1")


[![Video2](https://img.youtube.com/vi/KHZWj_-BlIg/0.jpg)](https://www.youtube.com/watch?v=KHZWj_-BlIg "Video 2")


[![Video3](https://img.youtube.com/vi/1D_HvjxB3Ps/0.jpg)](https://www.youtube.com/watch?v=1D_HvjxB3Ps "Video 3")


[![Video4](https://img.youtube.com/vi/ShU00qFSM5g/0.jpg)](https://www.youtube.com/watch?v=ShU00qFSM5g "Video 4")

