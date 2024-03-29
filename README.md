# AI_Conda_Practice
The aim of this project is to fine-tune Faster R-CNN. The main idea is to try not to lose the information and weights it already has about the objects it's pretrained with (using the COCO dataset). If this isn't possible, then the plan is to adapt and fine-tune it conventionally.

Once I have a model trained with the data I want, the next objective is to create a video processor that returns the video marking the objects within bounding boxes.

## Project Status Update:

After many attempts, documentation, and forums, I have not been able to make it maintain recognition of the objects it comes pre-trained with. My conclusion is that, due to the structure and the way it functions, it's not possible. To make that happen, my two solutions are to add a few images of the objects you want it to maintain from COCO so that it "doesn't forget" them, or try to add another additional layer to the structure of Faster R-CNN responsible for learning the new objects (the latter solution seems very ineffective to me and would result in a poorly optimized model).

## File Content:

In each file, the operation of each one is briefly described, as well as that of a specific method. However, here's a legend of what each file/repository does:

- In&Output_Videos: This folder contains the input and output videos from the "ObjectDetector.ipynb" file that have been generated during the tests.

- PyTorchVisionLibs: This folder contains libraries that are useful for performing the fine-tuning of the model.

- annotations: This folder contains annotation files and labels, both from COCO and those generated by the "Coords_selector.ipynb" file.

- images: CIt contains images of three different types of objects. For testing purposes, only the images of keys have been used so far.

- BoxGenerator.ipynb: This notebook initially implemented a method to automate object detection (using a CNN and image processing to isolate pixels that could form an object) to extract coordinates for bounding boxes.

- Coords_Selector.ipynb: This notebook opens image after image from the specified folder, allowing you to dynamically select and draw bounding boxes on the images. In the opened window, pressing the "space" key moves to the next image, and pressing "d" deletes the last drawn bounding box.

- FasterRCNN_FineTuning.ipynb: This notebook provides a method for performing conventional fine-tuning on the Faster R-CNN model.

- FasterRCNN_FineTuning_v2.ipynb: This notebook provides a method for fine-tuning while attempting to remember the pre-trained objects from COCO.

- Image_Downloader.ipynb: This notebook downloads images from Google Images. After attempting to load more than 21 images for each search and not succeeding in any way, I chose to perform the search in different languages, and the majority of the images are different from those in the other languages (The images you download may be protected by copyright. Before using an image, make sure you check its license and the specific terms of reuse).

- ObjectDetector.ipynb: This notebook processes videos and returns them with bounding boxes drawn around the detected objects.

- ObjectDetectorCamera.ipynb: This project aims to implement real-time video processing using an Android camera (it will work at very few frames per second).