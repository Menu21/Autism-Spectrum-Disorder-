
# Overview

This project implements a video processing pipeline for detecting and tracking children and therapists in long-duration videos. The pipeline uses YOLOv8 for object detection and DeepSORT for tracking, combined with a re-identification model (OSNet) to handle appearance-based tracking. The output is a video with bounding boxes and unique IDs for each detected person.

# Table of Contents

## Requirements

- Python 3.x
- OpenCV
- YOLOv8 (Ultralytics)
- DeepSORT Realtime
- PyTorch
- TorchReID
- Google Colab 



## Setup

To deploy this project You can install the required Python packages using pip:

- Using Google Colab for GPU Acceleration

### You can run this pipeline on Google Colab, which provides free access to GPU acceleration. To enable GPU in Colab:


```bash
Go to Runtime > Change runtime type.
Set Hardware accelerator to GPU.
Click Save.

```
This will allow you to utilize GPU for faster model inference.

1. You can install the required Python packages using pip:

```bash
  pip install opencv-python-headless ultralytics deep_sort_realtime torch torchreid

```
2. Clone the Repository

```bash
  git clone <https://github.com/Menu21/Autism-Spectrum-Disorder-.git>

```
3. Download the YOLOv8 Model

Ensure you have the YOLOv8 model file (terapistchildbestwright.pt) available. You can place this file in the drive/MyDrive/ directory or adjust the path in the script accordingly.

4. Install yt-dlp

First, ensure that you have yt-dlp installed. You can install it using pip:

```bash
  !pip install yt-dlp

```
5. Download the Video

Use yt-dlp to download the video from YouTube. Replace the URL in the command below with the URL of the video you want to download:
```bash
 !yt-dlp https://www.youtube.com/watch?v=3mXFJ8S-boU&t=6s

```
6. Prepare the Video File
Place your input video file (autism2.mp4) in the appropriate directory, such as drive/MyDrive/, or adjust the path in the script.

7. The script will read the input video, perform object detection, and track individuals using YOLOv8 and DeepSORT. The processed video with bounding boxes and unique IDs will be saved as output_video.mp4

## Code Explanation

- Model Loading

The script loads the YOLOv8 model for object detection and the OSNet model for re-identification.

- Video Processing

The video is read frame by frame. Each frame is processed to detect and track individuals using YOLOv8 and DeepSORT.

- Object Detection and Tracking

YOLOv8 detects bounding boxes for children and therapists. DeepSORT, combined with appearance embeddings from the OSNet model, tracks these detections across frames.

- Output

The processed frames, with bounding boxes and unique IDs, are saved to an output video file.


