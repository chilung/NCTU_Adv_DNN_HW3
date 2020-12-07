# Introduction
This is a github for NCTU course "Selected Topics in Visual Recognition using Deep Learning" homework 3: Instance Segmentation.
I refer to facebook's contribution, detectron2.
All of my homework was completed and can be executed in Google colab.

# My Homework Program
The program I made in Google colab is also based on facebook detectron2's colab tuturial program.

[my homework colab](https://colab.research.google.com/drive/1UFly0z_NLrUSOfj9VG5hJWDbKzlg-z5E?usp=sharing)

# Reproduce The Result
This program is a self sustained program. The procedure is highlighted here:

1. Install pytorch and detectron.
2. After detectron2 installed, the runtime needs to be restarted. Thus you can see a code exit(0) to restart the runtime and an error message: "你的工作階段因不明原因而異常終止。" shown. This is a correct result. There is no problem to go on executing the program.
3. The program will download the dataset, including train_images.zip, pascal_train.json, test_images.zip, test.json. And train_images.zip amd test_images.zip will be automatically unzipped into ./train_images and ./test_images.
4. You can see the length of train dataset is 1349 and 20 categories in the dataset by checking coco.cats.

