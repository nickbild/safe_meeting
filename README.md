# Safe Meeting

Safe Meeting keeps an eye on you during your video conferences, and if it sees your underwear, the video is immediately muted.

Many of us are working from home during these unusual times, and as such, are spending lots of time on video calls.  While we may be all business up top during the workday, working from home affords some with additional...comfort...with the rest of their clothing.

Safe Meeting prevents embarrassing and unprofessional situations by stopping your video stream if certain attire that's inappropriate for business is detected.

## How It Works

A camera is connected to an NVIDIA Jetson Nano.  This camera is positioned immediately next to a webcam that is used for video conferences, such that it captures the same region.

The stream of images is classified by a [Convolutional Neural Network](https://github.com/nickbild/safe_meeting/blob/master/train.py).  If an image is determined to contain inappropriate business attire, a [REST API call](https://github.com/nickbild/safe_meeting/blob/master/infer_rt.py) is made to the computer running the video conference.

When the [REST API server](https://github.com/nickbild/safe_meeting/blob/master/api.py) receives a request, it simulates a keypress on the keyboard, which in turn shuts off the video stream in the video conferencing software.

## Media

YouTube:

Full Setup:

![full_setup](https://raw.githubusercontent.com/nickbild/safe_meeting/master/media/full_setup_sm.jpg)

Jetson Nano:

![jetson_nano](https://raw.githubusercontent.com/nickbild/safe_meeting/master/media/jetson_nano_sm.jpg)

## Bill of Materials

- 1 x NVIDIA Jetson Nano
- 1 x Raspberry Pi Camera v2

## About the Author

[Nick A. Bild, MS](https://nickbild79.firebaseapp.com/#!/)
