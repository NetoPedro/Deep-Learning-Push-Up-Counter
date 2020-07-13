# Deep Learning Exercise Repetitions Counter

**Disclaimer:** This project was developed to integrate with an Android application during a 24 hours hackathon. One of the key elements was to keep the model small, capable of performing well on phones and easy to train with data manually gathered during those 24 hours. Therefore, this a simplistic approach to the problem of counting push ups, pull ups and squats. 

## Demo (Youtube)

Click to open the youtube video.

[![Demo](https://img.youtube.com/vi/3LaeKHo5xk8/0.jpg)](https://www.youtube.com/watch?v=3LaeKHo5xk8 "Demo")
## Goal

This project aims to build a deep learning solution to count the repetitions of exercises such as push ups or pull ups. A model that can run on phones and that is possible to train with only a few hundred images. 

## Workflow 

- Gather videos from push ups 

- Use farneback optical flow algorithm to preprocess the videos frame by frame.

- Label individually a few hundred of images generated.

- Train a deep neural network using those images. 

- Develop a method to count the repetition from the analysis of the movement in the video.

- Process test videos using a pipeline composed of the farneback optical flow algorithm + the deep neural network + the algorithm to estimate the repetitions using the predictions of the network.

### Dataset construction

The dataset (available in ./data/) was constructed from several videos removed from youtube and some home-made videos. The videos were processed with the optical flow algorithm. This algorithm allowed to construct a new video with a few colours representing the movement of the subjects in the videos. 

Afterwards, from the recently generated videos some frames were selected and manually labeled. The labels used were "Moving Up", "Moving Down" or "Not Moving". The latter represents all kind of moves different from down and up. 

A validation set was also created to evaluate the performance of the algorithm. 

### Model training 

The model used was a small convolutional neural network built in Keras. The goal of the model was from the input frames, predict if the subject was moving down, up or not moving. The training was a simple process so the input was resized to 64x64. However, the result in the test set was not perfect, and this might indicate that some of the frames were wrongly labeled, or the dataset slightly skewed. In a more positive note, despicte the fact that the model was trained only on push ups, it was able to correctly predict pull ups in the test set. 

### Counting repetitions

To count the repetitions of an exercise, the movement of the subject was analysed frame by frame. And what was considered as a repetition was a change of state, for example for push ups when the subject moves from an "Up move" to a "Down move". This did not work immediately so a tolerance had to be built due to the accuracy of the model not being 100%. The current state of the subject was then changed to a specific movement if X consecutive frames were classified with that movement. This value of X can be changed exercise wise, and I have found that push ups and pull ups work better with different X values.

### Evaluation on a test video

Finally I have added some result videos to my youtube channel. 

[![Video1](https://img.youtube.com/vi/wf9ZE0j2Q_o/0.jpg)](https://www.youtube.com/watch?v=wf9ZE0j2Q_o "Video 1")


[![Video2](https://img.youtube.com/vi/KHZWj_-BlIg/0.jpg)](https://www.youtube.com/watch?v=KHZWj_-BlIg "Video 2")


[![Video3](https://img.youtube.com/vi/1D_HvjxB3Ps/0.jpg)](https://www.youtube.com/watch?v=1D_HvjxB3Ps "Video 3")


[![Video4](https://img.youtube.com/vi/ShU00qFSM5g/0.jpg)](https://www.youtube.com/watch?v=ShU00qFSM5g "Video 4")

