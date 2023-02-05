# Face-Recognition

NECESSARY COMMANDS:
```
git clone https://github.com/Ayush-Balodi/Face-Recognition.git
open the repo in cmd
```

## Detect Faces in Image

=> cd "Detect Faces In Images"
=> python FaceDetection.py --image sample2.jpg --prototxt deploy.prototxt.txt --model res10_300x300_ssd_iter_140000.caffemodel

## Detect Faces In Video

=> cd "Detect Faces In Video"
=> python FaceDetectionVideo.py --prototxt deploy.prototxt.txt --model res10_300x300_ssd_iter_140000.caffemodel

## Face Recogniton
1> Extract embeddings
2> Train the model based on the embeddings and store the labelled dataset 
3> Recognize the test data using the trained data

![image](https://user-images.githubusercontent.com/87846532/216811154-34230cd2-6f8d-4d09-a3b8-d0b1996b9fb2.png)

1> COMMAND TO EXTRACT EMBEDDINGS : python extract_embeddings.py --dataset dataset --embeddings output/FaceRecognition_embed.pickle --detector face_detection_model --embedding-model openface_nn4.small2.v1.t7

2> COMMAND TO TRAIN THE MODEL : python train_model.py --embeddings output/FaceRecognition_embed.pickle --recognizer output/FaceRecognition_recognizer.pickle --le output/FaceRecognition_label.pickle

3> COMMAND TO RECOGNIZE FACE IN IMAGE : python recognize.py --detector face_detection_model --embedding-model openface_nn4.small2.v1.t7 --recognizer output/FaceRecognition_recognizer.pickle --le output/FaceRecognition_label.pickle --image images/test1.jpg

3> COMMAND TO RECOGNIZE FACE IN VIDEO : python recognize_video.py --detector face_detection_model --embedding-model openface_nn4.small2.v1.t7 --recognizer output/FaceRecognition_recognizer.pickle --le output/FaceRecognition_label.pickle
