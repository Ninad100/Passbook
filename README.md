# Passbook
Bank passbook details extraction

The project is about creating a ML pipeline which will extract useful information from the image of first page of passbook. Currently the process is done manually , as an Engineer our job is to automate the process as much as possible.

I performed the task in two different ways.

The first way is more general way for getting results. And second way is by using Deep Learning (code is attached).

First way :
This is straigt forward conventional method which failed to give proper results.

*Pipeline for first way* 
1. Set the current working directory as a directory from where we want to take input image (passbook).
2. Take the passbook image from that input as a input .
3. To get the best results from OCR convert the image into gray image.
4. After conversion appply this image directly to tesseract OCR.
5. get the text output and store it in text file.
6. Read the text file line by line and get the desired fields at output.
But output of OCR failed very badly in this approach hence next steps are not prformed.

The best approch :

DEEP LEARNING APPROACH :

This approach is used by me. The code for this approach is attached.

Pipeline stages :
1. Set the current working directory.
2. Get the input image folder and use the images as input.
3. Get the paths for frozen detection path (.pb ) file. Get path for label maps.
4. Loading the label map and category indices.
5. read the image and convert rgb image to gray image.
6. Load the trained model. and fed input image to model and start the detection.
7. Get the bounding boxes of the detected fields i.e. Name , account no. and ifsc code.
8. Get the coordinates of bounding boxes . and crop the image 3 times using those coordinates .
9. Pass these cropped images to OCR .
10. store the result of OCR in file.

This is perfect ML/DL pipeline to extract the results from the passbook input.
