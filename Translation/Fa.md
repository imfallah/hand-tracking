<img src="https://user-images.githubusercontent.com/73097560/115834477-dbab4500-a447-11eb-908a-139a6edaec5c.gif"><br><br>
<h1 align="center">👨🏽‍💻✋🏽ردیابی دست</h1>



### 🌏 مطالعه مقاله به  [English](https://github.com/imfallah/hand-tracking/)

### ⚡چک کردن [الزامات](https://github.com/imfallah/hand-tracking/blob/main/requriments.md)




<img src="https://user-images.githubusercontent.com/73097560/115834477-dbab4500-a447-11eb-908a-139a6edaec5c.gif"><br><br>
<p align="center">
<img src="https://img.shields.io/badge/language-python-blue?style"/><img src="https://img.shields.io/github/stars/imfallah/hand-tracking"/><img src="https://img.shields.io/github/forks/imfallah/hand-tracking"/>
</p>




<h4 align="center">[🛑کلا 5 دقیقه وقت بزار برای خوندش⚠👁‍🗨]</h4>

مطالعه فهرست مطالب✅✔
=================

<!--ts-->

* 🙌🏽[آنالیز دست چیست؟](#%D8%A2%D9%86%D8%A7%D9%84%DB%8C%D8%B2-%D8%AF%D8%B3%D8%AA-%DA%86%DB%8C%D8%B3%D8%AA)
   
* 🔸[نصب کن!⚠](#%D9%86%D8%B5%D8%A8-%DA%A9%D9%86-)

* 🔸[آنالیز کد 👨🏽‍💻](#%D8%A2%D9%86%D8%A7%D9%84%DB%8C%D8%B2-%DA%A9%D8%AF-)
   * 💫[ورودی کد](#0%EF%B8%8F%E2%83%A3%D9%88%D8%B1%D9%88%D8%AF%D8%AF%DB%8C-%D9%87%D8%A7%DB%8C-%DA%A9%D8%AF)
   * 💫[تشخیص دست](#%D8%AA%D8%B4%D8%AE%DB%8C%D8%B5-%D8%AF%D8%B3%D8%AA)
   * 💫[پیداکردن دست](#1%EF%B8%8F%E2%83%A3%D9%BE%DB%8C%D8%AF%D8%A7%DA%A9%D8%B1%D8%AF%D9%86-%D8%AF%D8%B3%D8%AA)
   * 💫[تشخص مفصل های دست](#2%EF%B8%8F%E2%83%A3%D8%AA%D8%B4%D8%AE%D8%B5%DB%8C-%D9%85%D9%81%D8%A7%D8%B5%D9%84-%D8%AF%D8%B3%D8%AA)
   * 💫[اصلی](
#3%EF%B8%8F%E2%83%A3%D8%A7%D8%B5%D9%84%DB%8C--)
   


* 🔸[ویترین💯🌏](#%D9%88%DB%8C%D8%AA%D8%B1%DB%8C%D9%86)
   * 🥇[ویدیو از پروژه📺](#%D9%88%DB%8C%D8%AF%DB%8C%D9%88-%D8%A7%D8%B2-%D9%BE%D8%B1%D9%88%DA%98%D9%87-)
    
* 🎁[ارتباط با من 🎃](#%D8%A7%D8%B1%D8%AA%D8%A8%D8%A7%D8%B7-%D8%A8%D8%A7-%D9%85%D9%86-)
<!--te-->
<h1 align="center">آنالیز دست چیست؟🙌🏽</h1>
<p align="center">
<img src="https://github.com/imfallah/hand-tracking/blob/main/public/landmark.png" width="300" height="300">
</p>
`تشخیص دست یک کار بینایی ماشینی است` که شامل شناسایی و ردیابی دست ها در تصاویر دیجیتال یا جریان های ویدئویی است. این کار به دلیل تنوع در ظاهر دست و حرکات پیچیده ای که دست ها می توانند انجام دهند، چالش برانگیز است. تشخیص دست در برنامه های مختلف مانند:

- تشخیص زبان اشاره✅
- کنترل با حرکات دست✅
- واقعیت مجازی و افزوده✅
- بازی ها✅
- امنیت و نظارت✅
در این رویکرد، OpenCV یک کتابخانه محبوب برای پردازش تصویر و ویدئو است و MediaPipe یک چارچوب یادگیری ماشینی چند منظوره است که مدل‌های از پیش آموزش‌دیده‌شده‌ای را برای وظایف بینایی ماشین مانند تشخیص چهره، تشخیص دست و تخمین پوس ارائه می‌دهد.


# نصب کن ⚠

## ماژول ها رو با استفاده از  pipنصب کن:

```python
pip insall opencv-python
pip install mediapipe
pip install time
```


> [!CAUTION]
>> 
> - اگر در این قسمت خطایی دارید، بررسی کنید [requriments](https://github.com/imfallah/hand-tracking/blob/main/requriments.md)




نصب موجود را به روز کنید: `pip3 install (کتابخانه شما) -- ارتقاء`
(تا حد امکان به روز رسانی کنید زیرا این کتابخانه در حال توسعه فعال است)

# آنالیز کد 🎃:

## 0️⃣وروددی های کد:

```python
import cv2
import mediapipe as mp
import time
```
## ✔تشخیص دست:
1. `class handDetector():`: این خط کد کلاسی به نام HandDetector را تعریف می کند.
2. `def __init__(self, mode=False, maxHands=2, detectionCon=0.5, modelCoplexity=1, trackCon=0,5):`: این ویژگی برای ایجاد یک شی از کلاس `handDetector` است. خطوط ورودی این تابع عبارتند از:
       - "حالت": حالت تشخیص دست (به طور پیش فرض غیرفعال است).
       - 'maxHands': تعداد دست هایی که می توان تشخیص داد.
       - `detectionCon`: آستانه تشخیص (پیش‌فرض 0.5).
       - `modelComplexity`: پیچیدگی مدل (1 به طور پیش فرض).
       - `trackCon`: آستانه ردیابی (به طور پیش فرض 0.5).
3. «self.mpHands = mp.solutions.hands»: در این خط، ماژول «hands» از کتابخانه «mediapipe» به عنوان «self.mpHands» تعریف می‌شود.
4. `self.hands = self.mpHands.Hands(self.mode, self.maxHands, self.modelCoplex, self.detectionCon, self.trackCon)`: در این خط یک شی از کلاس ``Hands`` با مشخص شده توکن ها ایجاد شده است
5. `self.mpDraw = mp.solutions.drawing_utils`: در این خط، ماژول «drawing_utils» از کتابخانه «mediapipe» به عنوان «self.mpDraw» تعریف می‌شود.

به طور خلاصه، این کد یک کلاس "handDetector" را تعریف می کند که برای تشخیص دست ها در تصاویر استفاده می شود. این کلاس از ماژول های 'hands' و 'drawing_utils' در کتابخانه 'mediapipe' استفاده می کند.
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
## 1️⃣پیداکردن دست:
1. `def findHands(self, img, draw=True):`: این تابع یک تصویر ورودی به نام "img" و یک پارامتر به نام "draw" را می پذیرد. پارامتر "draw" به طور پیش فرض روی "True" تنظیم شده است.
2. `imgRGB = cv2.cvtColor(img, cv2.COLOR_BGR2RGB)`: در این خط، تصویر ورودی از فضای رنگی BGR به RGB تبدیل می شود.
3. `self.results = self.hands.process(imgRGB)`: در این خط، عقربه ها در تصویر شناسایی شده و نتایج در متغیر `self.results` ذخیره می شود.
4. `if self.results.multi_hand_landmarks:`: اگر عقربه های شناسایی شده در تصویر وجود دارد، دستورات را در داخل بلوک شرطی اجرا کنید.
5. `for handLms در self.results.multi_hand_landmarks:`: برای هر عقربه شناسایی شده، دستورات را در داخل حلقه اجرا کنید.
6. "if draw: self.mpDraw.draw_landmarks(img, handLms, self.mpHands.HAND_CONNECTIONS)": اگر پارامتر "draw" "True" باشد، نقاط مربوط به عقربه ها روی تصویر نمایش داده می شود.
7. 'return img': تصویر نهایی با نقاط مربوط به عقربه ها برگردانده می شود.

به طور خلاصه، این تابع تصویر ورودی را پردازش می کند و نقاط مربوط به عقربه های روی آن را نمایش می دهد
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

## 2️⃣تشخصی مفاصل دست:
1. `def findpos(self, image, handNO=0, draw=True):`: این تابع یک تصویر ورودی به نام "image"، پارامتری به نام "handNO" (که به طور پیش فرض روی 0 تنظیم شده است) می گیرد و یک عدد را می پذیرد. پارامتر با نام "draw". پارامتر "draw" به طور پیش فرض روی "True" تنظیم شده است.
2. `lmlist = []`: در این خط یک لیست خالی با نام `lmlist` تعریف شده است.
3. `if self.results.multi_hand_landmarks:`: اگر عقربه های شناسایی شده در تصویر وجود دارد، دستورات را در داخل بلوک شرطی اجرا کنید.
4. «myHand = self.results.multi_hand_landmarks[handNO]»: در این خط، عقربه مربوط به عدد «handNO» از عقربه‌های شناسایی‌شده در تصویر انتخاب می‌شود.
5. `for id, lm in enumerate(myHand.landmark):`: برای هر نقطه مربوط به عقربه، دستورات را در داخل حلقه اجرا کنید.
6. `h, w, c = image.shape`: در این خط ابعاد تصویر ورودی (ارتفاع، عرض و تعداد کانال) در متغیرهای `h`, `w` و `c` ذخیره می شود.
7. `cx, cy, = int(lm.x * w), int(lm.y *h)`: در این خط مختصات (x,y) نقطه مربوط به عقربه در تصویر محاسبه می شود. .
8. `lmlist.append([id, cx, cy])`: مختصات نقاط عقربه در لیست lmlist ذخیره می شود.
9. «if draw: cv2.circle(image, (cx, cy), 5, (255, 0, 255), cv2.FILLED)»: اگر پارامتر «draw» برابر «True» باشد، دایره ای با مرکز در مختصات نقطه مربوط به عقربه و شعاع 5 روی تصویر نمایش داده می شود.
10. 'return lmlist': لیست نقاط مربوط به عقربه به عنوان خروجی تابع برگردانده می شود.

"به طور خلاصه، این عملکرد نقاط مربوط به دست ها را در تصویر ورودی شناسایی و نمایش می دهد".
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
## 3️⃣اصلی  :
1. `def main():`: این خط کد تابعی به نام اصلی را تعریف می کند.
2. `pTime = 0`: در این خط، متغیر `pTime` با مقدار صفر مقداردهی اولیه می شود.
3. `cap = cv2.VideoCapture(0)`: در این خط یک شی از کلاس `VideoCapture` ایجاد می شود که برای گرفتن تصاویر از دوربین استفاده می شود.
4. `detector = handDetector()`: در این خط یک شی از کلاس `handDetector` ایجاد می شود.
5. `while True:`: حلقه بی نهایت شروع می شود.
6. `success, img = cap.read()`: در این خط یک تصویر از دوربین گرفته شده و در متغیر `img` ذخیره می شود.
7. `img = detector.findHands(img)`: در این خط، تابع "findHands" شیء "detector" روی تصویر اجرا می شود و تصویر با نقاط مربوط به عقربه ها به روز می شود.
8. `lmlist = detector.findpos(img)`: در این خط، تابع 'findpos' شی 'detector' روی تصویر اجرا می شود و لیست نقاط مربوط به عقربه ها به دست می آید.
9. `if len(lmlist) != 0: print(lmlist[4])`: اگر تعداد نقاط مربوط به عقربه ها بیش از صفر باشد، مختصات نقطه پنجم (شماره 4) از لیست نمایش داده می شود. .
10. `cTime = time.time()`: در این خط زمان جاری ذخیره می شود.
11. `fps = 1 / (cTime - pTime)`: در این خط میانگین فریم در ثانیه محاسبه می شود.
12. "pTime = cTime": مقدار "pTime" به زمان فعلی تغییر می کند.
13. `cv2.putText(img, str(int(fps)), (10, 70), cv2.FONT_HERSHEY_PLAIN, 3, (255, 0, 255), 3`: در این خط میانگین فریم ها در تصویر نمایش داده خواهد شد.
14. `cv2.imshow("Image", img)": تصویر نمایش داده می شود.
15. `cv2.waitKey(1)`: منتظر یک ورودی کلید از صفحه کلید است.

به طور خلاصه، این کد از دوربین عکس می گیرد، دست ها را تشخیص می دهد و نقاط مربوط به عقربه ها را روی تصویر نمایش می دهد.
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



## ویترین🌝

### ویدیو وعکس از پروژه 📺


# ارتباط با من 🎈🎃

<a herf="https://www.buymeacoffee.com/jokernets"><img src="https://cdn.buymeacoffee.com/buttons/v2/arial-yellow.png" alt="Buy Me A Coffee" width="180px">
<a href="mailto:joker.until33@gmail.com"><img align="center" width="60px" src="https://github.com/edent/SuperTinyIcons/raw/master/images/svg/gmail.svg" style="max-width: 100%;"></a><a href="https://www.linkedin.com/" target="blank"><img align="center" src="https://raw.githubusercontent.com/rahuldkjain/github-profile-readme-generator/master/src/images/icons/Social/linked-in-alt.svg" alt="https://www.linkedin.com/in/mohammadfallahnejad/" height="40" width="60" /></a>
