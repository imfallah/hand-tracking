<img src="https://user-images.githubusercontent.com/73097560/115834477-dbab4500-a447-11eb-908a-139a6edaec5c.gif"><br><br>
<h1 align="center">Hand Tracking👨🏽‍💻✋🏽</h1>



### 🌏 Readme in [فارسی](https://github.com/jokernets/hand-tracking/tree/main/Fa.md)


<img src="https://user-images.githubusercontent.com/73097560/115834477-dbab4500-a447-11eb-908a-139a6edaec5c.gif"><br><br>
<p align="center">
<img src="https://img.shields.io/badge/language-python-blue?style"/><img src="https://img.shields.io/github/stars/imfallah/hand-tracking"/><img src="https://img.shields.io/github/forks/imfallah/hand-tracking"/>
</p>
<div align="center">



<a href="https://github.com/imfallah/snake-game" title="Go to GitHub repo"><img src="https://img.shields.io/static/v1?label=imfallah&message=snake-game&color=green&logo=github" alt="imfallah - snake-game"></a>
<a href="https://github.com/imfallah/snake-game" title="Go to GitHub repo"><img src="https://img.shields.io/static/v1?label=imfallah&message=password-generatoe&color=red&logo=github" alt="imfallah - password-generate"></a>

</div>

<a href="https://github.com/imfallah/snake-game/actions?query=workflow:%22snake-game%22"></a>

<h4 align="center">[🛑Time to study 5 minutes⚠👁‍🗨]</h4>

Table of contents✅✔
=================

<!--ts-->

   * 🙌🏽[HAND TRACKING](#hand-tracking)
   
   * 🔸[Installation⚠](#installation)

   * 🔸[About Code👨🏽‍💻](#analiys-code-)
     * 💫[importing](#0%EF%B8%8F%E2%83%A3importing)
     * 💫[Find Detector](#hand-detector)
     * 💫[find Hand](#1%EF%B8%8F%E2%83%A3find-hand)
     * 💫[find pose](#2%EF%B8%8F%E2%83%A3find-pose)
     * 💫[Main](#3%EF%B8%8F%E2%83%A3main-)


   * 🔸[Mor Example💯🌏](#more-examples-and-showcase-)
     * 🥇[Project Video📺](#video-image-of-the-app-)
    
   * 🎁[`CONNECT ME🎃`](#connect-me)
   * 
<!--te-->
<h1 align="center">Hand Tracking🙌🏽</h1>
<p align="center">
<img src="https://github.com/jokernets/hand-tracking/blob/main/landmark.png" width="300" height="300">
</p>

`Hand recognition is a machine vision` task that involves identifying and tracking hands in digital images or video streams. This task is challenging due to the variability in hand appearance and the complex movements the hands can perform. Hand recognition in various programs such as:

- Sign language recognition
- Control with hand gestures
- Virtual and augmented reality
- Games
- Security and surveillance



In this approach, OpenCV is a popular library for image and video processing, and MediaPipe is a multipurpose machine learning framework that provides pre-trained models for machine vision tasks such as face recognition, hand recognition, and pose estimation.






# Installation⚠

## Install the Library with pip:

```python
pip insall opencv-python
pip install mediapipe
pip install time
```

Update existing installation:`pip3 install (YOUR LIBRARY) --upgrade`
(update as often as possible because this library is under active development)

# Abot Code🎃:

## 0️⃣Importing:

```python
import cv2
import mediapipe as mp
import time
```
## `Hand Detector`:
1. `class handDetector():`: This line of code defines a class called `handDetector`.
2. `def __init__(self, mode=False, maxHands=2, detectionCon=0.5, modelCoplexity=1, trackCon=0.5):`: This property is for creating an object from the `handDetector` class. The input lines of this function are:
      - `mode': hands detection mode (disabled by default).
      - `maxHands`: The number of hands that can be detected.
      - `detectionCon`: detection threshold (default 0.5).
      - `modelComplexity`: model complexity (1 by default).
      - `trackCon`: tracking threshold (0.5 by default).
3. `self.mpHands = mp.solutions.hands`: In this line, the `hands` module from the `mediapipe` library is defined as `self.mpHands`.
4. `self.hands = self.mpHands.Hands(self.mode, self.maxHands, self.modelComplex, self.detectionCon, self.trackCon)`: In this line, an object of ``Hands`` class with specified tokens has been is created
5. `self.mpDraw = mp.solutions.drawing_utils`: In this line, the `drawing_utils` module from the `mediapipe` library is defined as `self.mpDraw`.

Briefly, this code defines a ``handDetector'' class that is used to detect hands in images. This class uses the `hands` and `drawing_utils` modules in the `mediapipe` library.
```python
class handDetector():
    def __init__(self, mode=False, maxHands=2, detectionCon=0.5, modelComplexity=1, trackCon=0.5):
        self.mode = mode
        self.maxHands = maxHands
        self.modelComplex = modelComplexity
        self.detectionCon = detectionCon
        self.trackCon = trackCon
        self.mpHands = mp.solutions.hands
        self.hands = self.mpHands.Hands(self.mode, self.maxHands, self.modelComplex, self.detectionCon, self.trackCon)
        self.mpDraw = mp.solutions.drawing_utils

```
## 1️⃣`Find Hand`:
1. `def findHands(self, img, draw=True):`: This function accepts an input image named `img` and a parameter named `draw`. ``draw'' parameter is set to ``True'' by default.
2. `imgRGB = cv2.cvtColor(img, cv2.COLOR_BGR2RGB)`: In this line, the input image is converted from BGR color space to RGB.
3. `self.results = self.hands.process(imgRGB)`: In this line, hands are detected in the image and the results are stored in the `self.results` variable.
4. `if self.results.multi_hand_landmarks:`: If there are detected hands in the image, execute commands inside the conditional block.
5. `for handLms in self.results.multi_hand_landmarks:`: For each detected hand, execute commands inside the loop.
6. `if draw: self.mpDraw.draw_landmarks(img, handLms, self.mpHands.HAND_CONNECTIONS)`: If the `draw` parameter is ``True'', the points corresponding to the hands will be displayed on the image.
7. `return img`: The final image with the points corresponding to the hands is returned.

`In short, this function processes the input image and displays the points corresponding to the hands on it`
```python
    def findHands(self, img, draw=True):
        imgRGB = cv2.cvtColor(img, cv2.COLOR_BGR2RGB)
        self.results = self.hands.process(imgRGB)
        # print(results.multi_hand_landmarks)
        if self.results.multi_hand_landmarks:
            for handLms in self.results.multi_hand_landmarks:
                if draw:
                    self.mpDraw.draw_landmarks(img, handLms, self.mpHands.HAND_CONNECTIONS)
        return img
```

## 2️⃣*`Find Pose`:
1. `def findpos(self, image, handNO=0, draw=True):`: This function takes an input image named `image`, a parameter named `handNO` (which is set to 0 by default ) and accepts a parameter named `draw`. ``draw'' parameter is set to ``True'' by default.
2. `lmlist = []`: In this line, an empty list named `lmlist` is defined.
3. `if self.results.multi_hand_landmarks:`: If there are detected hands in the image, execute commands inside the conditional block.
4. `myHand = self.results.multi_hand_landmarks[handNO]`: In this line, the hand corresponding to the number `handNO` is selected from the detected hands in the image.
5. `for id, lm in enumerate(myHand.landmark):`: for each point related to the hand, execute commands inside the loop.
6. `h, w, c = image.shape`: In this line, the dimensions of the input image (height, width and number of channels) are stored in the variables `h`, `w` and `c`.
7. `cx, cy, = int(lm.x * w), int(lm.y * h)`: In this line, the coordinates (x, y) of the point corresponding to the hand in the image are calculated.
8. `lmlist.append([id, cx, cy])`: The coordinates of the hand points are stored in the `lmlist` list.
9. `if draw: cv2.circle(image, (cx, cy), 5, (255, 0, 255), cv2.FILLED)`: If the parameter `draw` is equal to `True`, a circle with center In the coordinates of the point corresponding to the hand and radius 5 is displayed on the image.
10. `return lmlist': The list of points related to the hand is returned as the output of the function.

`In short, this function detects and displays points related to hands in the input image`
```python
    def findpos(self, image, handNO=0, draw=True):
        lmlist = []
        if self.results.multi_hand_landmarks:
            myHand = self.results.multi_hand_landmarks[handNO]
            for id, lm in enumerate(myHand.landmark):
                # print(id, lm)
                h, w, c = image.shape
                cx, cy, = int(lm.x * w), int(lm.y * h)
                # print(id, cx, cy)
                lmlist.append([id, cx, cy])
                if draw:
                    cv2.circle(image, (cx, cy), 5, (255, 0, 255), cv2.FILLED)
        return lmlist
```
## 3️⃣`Main` :
1. `def main():`: This line of code defines a function named `main`.
2. `pTime = 0`: In this line, the `pTime` variable is initialized with zero value.
3. `cap = cv2.VideoCapture(0)`: In this line, an object of the `VideoCapture` class is created, which is used to capture images from the camera.
4. `detector = handDetector()`: In this line, an object of the `handDetector` class is created.
5. `while True:`: The infinite loop starts.
6. `success, img = cap.read()`: In this line, an image is taken from the camera and stored in the `img` variable.
7. `img = detector.findHands(img)`: In this line, the `findHands` function of the `detector` object is run on the image and the image is updated with the points corresponding to the hands.
8. `lmlist = detector.findpos(img)`: In this line, the `findpos` function of the `detector` object is executed on the image and the list of points related to the hands is obtained.
9. `if len(lmlist) != 0: print(lmlist[4])`: If the number of points related to hands is more than zero, the coordinates of the fifth point (number 4) from the list will be displayed.
10. `cTime = time.time()`: In this line, the current time is stored.
11. `fps = 1 / (cTime - pTime)`: In this line, the average frames per second is calculated.
12. `pTime = cTime`: The value of `pTime` is changed to the current time.
13. `cv2.putText(img, str(int(fps)), (10, 70), cv2.FONT_HERSHEY_PLAIN, 3, (255, 0, 255), 3)`: In this line, the average of frames in the display image It will be given.
14. `cv2.imshow("Image", img)`: The image is displayed.
15. `cv2.waitKey(1)`: waits for a key input from the keyboard.

`In short, this code takes images from the camera, detects the hands and displays the points corresponding to the hands on the image`
```python
def main():
    pTime = 0
    cap = cv2.VideoCapture(0)
    detector = handDetector()
    while True:
        success, img = cap.read()
        img = detector.findHands(img)
        lmlist = detector.findpos(img)
        if len(lmlist) != 0:
            print(lmlist[4])
        cTime = time.time()
        fps = 1 / (cTime - pTime)
        pTime = cTime
        cv2.putText(img, str(int(fps)), (10, 70), cv2.FONT_HERSHEY_PLAIN, 3,
                    (255, 0, 255), 3)
        cv2.imshow("Image", img)
        cv2.waitKey(1)
if __name__ == "__main__":
    main()
```
<img src="https://user-images.githubusercontent.com/73097560/115834477-dbab4500-a447-11eb-908a-139a6edaec5c.gif"><br><br><img src="https://user-images.githubusercontent.com/73097560/115834477-dbab4500-a447-11eb-908a-139a6edaec5c.gif"><br><br>



## More Examples and Showcase 👑

<img src="https://github.com/imfallah/hand-tracking/blob/main/pic2.png" width=300px>

<img src="https://github.com/imfallah/hand-tracking/blob/main/public/Untitled%20Project.gif" width=300px>



# `𝐂𝐨𝐧𝐧𝐞𝐜𝐭 𝐌𝐞`🎈🎃

<a herf="https://www.buymeacoffee.com/jokernets"><img src="https://cdn.buymeacoffee.com/buttons/v2/arial-yellow.png" alt="Buy Me A Coffee" width="180px">
<a href="mailto:joker.until33@gmail.com"><img align="center" width="60px" src="https://github.com/edent/SuperTinyIcons/raw/master/images/svg/gmail.svg" style="max-width: 100%;"></a><a href="https://www.linkedin.com/" target="blank"><img align="center" src="https://raw.githubusercontent.com/rahuldkjain/github-profile-readme-generator/master/src/images/icons/Social/linked-in-alt.svg" alt="https://www.linkedin.com/in/mohammadfallahnejad/" height="40" width="60" /></a>
