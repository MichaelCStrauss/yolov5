# Group 12 Milestone Three

For this submission, we are using a YOLOv5 object detection network. We have used this because it was just as easy to use as AlexNet and was very fast to train accurately. The object detection will be very useful for future milestones.

To train our network, we used a image generation script (see `generate_dataset.py`). This randomly scales and places one of 12 angles of a coke can and/or sheep onto a random background image. It also produces the training labels required to finetune YOLO on our data.

We have used the smallest YOLO network, YOLOv5, with 7.5M parameters. On my desktop, this is able to run at ~45 FPS (using a GTX 1070). Hopefully, this is sufficient for real-time use for a later milestone.

## Instructions

This is hopefully simple to run:

1. Install all the requirements in `requirements.txt`: `pip install -r requirements.txt`
1. Place images for the test dataset in `test_dataset/`. The script assumes that images will be placed into folders designating the label, as in `train` and `test`:
    `/test_dataset/sheep`, `/test_dataset/coke`, `/test_dataset/neither` each containing the image files.
1. Run: `python3 nn_test.py --source "test_dataset/**/*.png" --weights runs/exp10/weights/last.pt --save-txt`
1. The results of each image file and the overall image accuracy are printed to the terminal.
1. If you wish to further observe training outcomes, view the files in `inference/output`. There will be an annotated image file for each prediction.


I have provided a sample output when we run the network on the provided `test` dataset in `provided_test_data_run.txt`. Note: `sheep/69.png` also contains a coke can hence incorrect classification. There are also a couple of example output images in `inference/output`
