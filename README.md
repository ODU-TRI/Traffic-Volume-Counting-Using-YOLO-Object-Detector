# Traffic Volume Counting Using YOLO Object Detector

This is a program to automatically detect and count vehicles passing through a corridor in a certain direction. For this purpose, we implemented a commonly used object detector called YOLO (You only look once) which takes the input frames from a video file and outputs a bounding box for every vehicle visible in the image. We used [YOLO v5](https://github.com/ultralytics/yolov5/tree/master) for this purpose. Next, we defined a reference line and a direction set by the user to determine where the bounding box stands in relation to this line. This line is defined by taking two points from the user. Once the center of the bounding box for a certain vehicle passes this reference line between two consecutive frames, we count it as a new vehicle and update the total count.

This process is repeated for every frame of the input video. We use [OpenCV](https://opencv.org/) for processing the video file, extracting frames, and drawing additional information on the output video containing the count. We also store the count data in a CSV file with the timestamp for each vehicle detected. [Pandas](https://pandas.pydata.org/) was used for this purpose. This data can then be aggregated to extract counts for any desired interval such as hourly count. This process does not need any individual training and only uses off-the-shelf resources readily available to public.*

* [ChatGPT](https://chat.openai.com) has also been used to produce some of the helper functions.

  
# Installation and Usage

### Option 1: Use requirements.txt and pip

**Step 1**: Install [Anaconda](https://docs.anaconda.com/free/anaconda/install/index.html).

**Step 2**:Create a virtual environment:

```python
conda create --name VolumeCount
```

**Step 3**:Activate the new virtual environment:

```python
conda activate VolumeCount
```

**Step 4**: Install requirements using:

```python
pip install -r requirements.txt
```
**Step 5**: Add the virtual environment to Jupyter notebook:

```python
pip install --user ipykernel
```
```python
python -m ipykernel install --user --name=VolumeCount
```

**Step 6**: open Jupyter notebook and change kernel to VolumeCount.

### Option 2: Use Google Colab environment

Follow instructions on [this Google colab page](https://colab.research.google.com/drive/1RNYT8CX6BvbfDkVuH4cAeFlehymLFzqo?usp=sharing).



## License
This project is licensed under the MIT License - see the [LICENSE.md](LICENSE.md) file
