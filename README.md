# Pedestrians intention detection using Yolo11 and Pedestrians profile

![Pedestrian Detection Architecture](Model Architecture.drawio.png)


### 1. **YOLO Object Detection (Pedestrian Detection)**
   - **Automatic Detection**: YOLO detects pedestrians in your images or video feed and generates bounding boxes.
   - **Initial Prediction (Intent to Cross (HIGH,LOW) , Crossing, Walking or Standing)**: Based on the YOLO output, you can classify whether a pedestrian is crossing or standing using additional features like age, gender, and clothing.

### 2. **Extract Additional Features (Age, Gender, Clothes)**
   - Use pre-trained models to extract the age, gender, and clothes information for each detected pedestrian (as described in previous responses).
   - These features (age, gender, and clothes) will be used alongside the YOLO prediction (crossing or standing) to make a more informed decision.

### 3. **Manual Labeling (Crossing or Not)**
   - Once you have all the features (YOLO output + age, gender, clothes), you will need to manually label whether the pedestrian is indeed **crossing** or **not crossing**.
   - This can be done by reviewing the detected pedestrian's behavior, taking into account not only their appearance (age, gender, clothes) but also how they are interacting with the environment in the video/image (for instance, moving towards a crosswalk could indicate crossing).
   
   - **Manual Labeling**: After combining the YOLO detections and additional features, you'll assign the final label **"crossing"** or **"not crossing"** based on what you observe in the image or video. This manual labeling could be done in the following way:
     - **Visual Review**: After the pedestrian is detected and the additional features are extracted, check if the pedestrian is crossing (in the context of the image or video) or just standing still. If they’re standing, label it as **"not crossing"**; if they are moving towards the crosswalk or walking on the road, label it as **"crossing"**.

### 4. **Using Labeled Data for Training**
   - **Dataset Creation**: After labeling enough examples manually, you will have a dataset that contains images (or frames from a video) where each pedestrian detection is labeled as either **"crossing"** or **"not crossing"**.
   - **Training**: You can then use this labeled dataset to train a model (e.g., a decision tree, random forest, or neural network) that can predict whether a pedestrian will cross or not based on the features (age, gender, clothes, YOLO output).

### 5. **Example Workflow for Manual Labeling:**
   - **Step 1**: Run YOLO on a video or a set of images to detect pedestrians.
   - **Step 2**: For each pedestrian detection, use additional models to predict their age, gender, and clothing.
   - **Step 3**: After all features are extracted (YOLO output, age, gender, clothes), you will manually check the context of the pedestrian and label them as **"crossing"** or **"not crossing"**.
   - **Step 4**: Store the labeled data, and use it to train or fine-tune a classification model.
