__author__ = 'samunvr'

import cv2
import sys
import os
import remove_pre_saved_files
import time



directory = '.' # create a directory for each person face
filename = raw_input('Enter a person name to generate a training set: ')
directory = directory + "/" + filename
if not os.path.exists(directory):
    os.mkdir(directory)
remove_pre_saved_files.scandirs(directory)

count = 0
start = time.time()
cascPath = '/home/sami/Google Drive/facerecognition/code/haarcascade_frontalface_alt.xml'
faceCascade = cv2.CascadeClassifier(cascPath)

video_capture = cv2.VideoCapture(0)


while True:
    # Capture frame-by-frame
    ret, frame = video_capture.read()
    if video_capture.isOpened() == 0:
        video_capture.open(0)

    gray = cv2.cvtColor(frame, cv2.COLOR_BGR2GRAY)
    cv2.imshow('video', frame)

    faces = faceCascade.detectMultiScale(
        gray,1.3,5
    )

    # Draw a rectangle around the faces

    for (x, y, w, h) in faces:
        cv2.rectangle(frame, (x, y), (x+w, y+h), (0, 255, 0), 2)
        cv2.rectangle(frame, (x,y), (x+w,y+h), (255,255,255))
        sub_face = frame[y:y+h, x:x+w]
        face_file_name = directory + "/frame_" + str(count) + ".jpg"
        cv2.imwrite(face_file_name, sub_face)
        count = count+1
        print count
        if count == 100:
            c ='q'
            if cv2.waitKey(1) & 0xFF == ord(c):
                break
            break


    # Display the resulting frame
    cv2.imshow('Video', frame)

    if cv2.waitKey(1) & 0xFF == ord('q'):
        break

# When everything is done, release the capture
video_capture.release()
cv2.destroyAllWindows()
end = time.time()
print end-start
