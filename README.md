# face_detection_training_data_generation_openCV
#This script is developed to generate a set of face images for a person in front of a camera. The objective is to use these images later for training a classifier to learn a each person's face models and use it for face verification use basic openCV function and machine learning techniques (KNN).
# The entire system is to recognize individuals based on their trained images so they can be used to authorized individuals to access houses, offices, computers, etc.
# look for the video that demonestrates the flow of this scrips
# I use pre-trained OpenCV haar cascade classifier for faces to detect faces in cameras 
# draw a rectangle around the detected faces
# crop the deteced faces and save it as jpg file

# you can create a unique folder for each person and saved the cropped images into their repsected folders so later you can label each person with a unique id(e.g, a person name), which later you can use it to identify each person by a setting a threshold for the confidence of the recognizer

# WATCH A DEMO AT : https://youtu.be/5rmAf3lJ7fk
