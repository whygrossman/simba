# Create tracking model using DeepLabCut

### Pipeline breakdown
this is something

### Part 1: Create DLC Project

### Part 2: Load DLC Project
- Extract Frames
- Label Frames
- Generate Training Set
- Download weights and train model
- Evaluate Model
- Analyze Videos

### Part 3: Improve the Model
- Extract more frames 
- Outlier correction

## Part 1: Create DLC Project
This section create a new project for your DLC tracking analysis.

<img src="https://github.com/sgoldenlab/tkinter_test/blob/master/images/createdlcmodel.png" width="400" height="200" />

### Step 1: Generate a new DLC project
blablabla

1. Go to `Tracking` --> `DeepLabCut` --> `Create DLC Model`. The following window will pop up.

<img src="https://github.com/sgoldenlab/tkinter_test/blob/master/images/createdlcmodel2.png" width="400" height="336" />

2. Enter the name of your project in `Project Name`

3. Enter your name in the `Experimenter Name`

> **Note:** Spaces are not allowed for your project name and experimenter name.

4. If you are only tracking one video, you can click on <img src="https://github.com/sgoldenlab/tkinter_test/blob/master/images/importsinglevideo.PNG" width="120" height="27" /> and the <img src="https://github.com/sgoldenlab/tkinter_test/blob/master/images/videofolder.PNG" width="274" height="27" /> in **green** color font should change to <img src="https://github.com/sgoldenlab/tkinter_test/blob/master/images/videopath.PNG" width="274" height="27" /> in **blue** font. Then click on `Browse File` to select the video.

5. If you are tracking multiple videos, click on <img src="https://github.com/sgoldenlab/tkinter_test/blob/master/images/importmultivideo.PNG" width="120" height="27" /> and the **green** color <img src="https://github.com/sgoldenlab/tkinter_test/blob/master/images/videofolder.PNG" width="274" height="27" /> will appear and click on `Browser Folder` to choose a folder with the videos. The default settings is always to **import multiple videos**.

6. Next, select the main directory that your project will be in. In `Working Directory` click `Browser Folder` and choose a directory.

7. Choose to apply Golden Aggression Config by checking the checkbox.

8. You can have a choice of copying all the videos to your DLC project folder by checking the `Copy Videos` checkbox.

9. Click `Create Project` to create your DLC project. The project will be located in the **working directory** that was set.


## Part 2: Load DLC Project
load dlc project

### Step 1: Check the settings in config.yaml file

1. Go to the project folder.

2. Double click on the config.yaml file and open it in Notepad.

3. Change the settings.

### Step 2: Load config.yaml file with GUI

1. Go to `Tracking` --> `DeepLabCut` --> `Load DLC Model`. The following window will pop up.

2. Under **Load Model**, click on `Browse File` and load the *config.yaml* file from the project folder.

### Step 3: Add additonal videos into project [Optional]

#### Single Video

1. Under **Single Video**, click on `Browse File` and select the video.

2. Click `Add single video`

#### Multiple Videos

1. Under **Multiple Videos**, click on `Browse Folder` and select the folder with only the videos.

2. Click `Add multiple videos`

### Step 4: Extract Frames DLC

1. Enter the numbers of frames that you wish to extract in the `numframes2pick` entry box.

2. Select the **Mode** of selecting the frames. 

`Automatic` selects the frames for you automatically. 

`Manual` allows you to select the frames.

3. Select the **Algorithm** to pick the frames. 

`Uniform` selects the frames uniformly in a series format. 

`KMeans` uses k-means clustering algorithm to select the frames randomly based on cluster. 

`Cluster Resize Width` is ......... explain please. The default is set to 30

`Cluster Step` is . idk man . The default is set to 1

4. Select **Cluster color**

5. If you wish to use **OpenCV** to extract frames you can check the `True` checkbox. If you wish to use **ffmpeg** then keep it uncheck.

6. Click `Extract Frames` to extract frames.

### Step 5: Label Frames

1. Under **Label Frames**, click on the `Label Frames` button and *DeepLabCut- Labelling ToolBox* will pop up.

2. At the botton left corner, click on `Load Frames`.

3. Choose the folder with your video name where your extracted frames are saved and click `Select Folder`. *They should be located at workingdirectory/yourproject/labeled-data/

4. Then you can start labelling frames. (insert link to label frames from dlc here)

### Step 6: Check Labels

1. Once all the frames are labelled. Under **Check Labels**, click on `Check Labelled Frames` to check the labelled frames.

### Step 7: Generate Training Set

1. Under **Generate Training Set**, click on the ` Generate training set` button to generate the training data set.

### Step 8: Train Network

`iteration` is 

`init_weight` is the initial weights to train the model

#### Training a new model

1. If you are training a new model and wanted to start from fresh. The `iteration` will be set to 0 by default and the `init_weight` will be set to resnet-50 by default

2. Hence, do not change the settings and just click `Train Network` button.

#### Training existed model

1. If you want to retrain a model, you can select the iteration in the `iteration` entry box and click `Update iteration`.

2. Then, you can click `Browse File` to find the model that you wish to retrain and click `Update init_weight` 

3. Click `Train Network` to start training your model.

### Step 9: Evaluate Network

1. Click on `Evaluate Network` to evaluate the trained model

### Step 10: Video Analysis

#### Single Video Analysis

1. Under **Single Video Analysis**, click on `Browse File` and select one of the video.

2. Click on `Single Video Analysis`

#### Multiple Videos Analysis

1. Under **Multiple Videos Analysis**, click on `Browse Folder` and select the video folder.

2. Enter the video format in `Video type` entry box (eg: mp4, avi). *Do **not** put any " . " dot in the entrybox (eg: .mp4, .flv, .avi, etc.)*

3. Click on `Multi Videos Analysis`

### Step 11: Plot Video Graph

1. Click on `Browse File` to select the video

2. Click on `Plot Results` 

### Step 12: Create Video
This step is to generate the video with labelled tracking points.

1. Click on `Browse File to select the video 

2. You can choose to save the frames with tracking points of the video by checking the `Save Frames` checkbox. This will result in a longer waiting time for this process.

3. Click on `Create Video`

## Part 3: Improve the Model
There are two ways that you can improve the current model.

1. To extract more frames to train the model

2. To correct the tracking points of the existing frames.

### Extract more frames
This step creates a temp.yaml file to automate the extract frames step.


