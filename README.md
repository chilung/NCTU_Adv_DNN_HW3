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
3. The program will download the dataset, including `train_images.zip`, `pascal_train.json`, `test_images.zip` and `test.json`. And `train_images.zip` and `test_images.zip` will be automatically unzipped into `./train_images` and `./test_images`.
4. You can see the length of train dataset is 1349 and the list of 20 categories by checking coco.cats.
5. Two functions `datasetCateId_2_modelCateId` and `modelCateId_2_datasetCateId` are used to transfer between dataset category id and model category id. It is because dataset category id is 1 ~ 20 and model category id should be 0 ~ 19.
6. In detectron2, the dataset should be registered, such as:
<pre><code>DatasetCatalog.register('tiny_voc_train', lambda: get_tiny_voc_dicts('./train_images', './pascal_train.json', 'train'))
MetadataCatalog.get('tiny_voc_train').thing_classes = tiny_voc_classes('./train_images', './pascal_train.json') </code></pre>
7. In `get_tiny_voc_dicts`, we split the 1349 samples in train dataset into train dataset (1079 samples) and validate dataset (270 samples) and specify by the third parameter 'train' or 'valid'.
8. In Inference & evaluation using the trained model section. I have uploaded 7 models I trained in my top mAP list: mAP 64.238% in epoch 48999, mAP 64.129% in epoch 41999, mAP 63.109% in epoch 33999, mAP 62.736% in epoch 61999, mAP 61.604% in epoch 56999, mAP 61.367% in epoch 52999 and mAP 60.899% in epoch 63999.
9. In the colab, I use mAP 64.238% in epoch 48999, `model_0048999.pth`, as a demo model.
