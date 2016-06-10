증강현실을 이용한 피아노 연주 보조 어플리케이션
===================


<br></br>

```
전체적인 프로젝트의 내용과 본인이 개발한 내용에 대해 집중적으로 작성했습니다.
```


<br></br>

<br></br>



##개발환경
-------------

| os     | tool   |language|
|:-------|:-------|:-------|
|Android |Android Studio, Unity3D, Vuforia SDK|C#, Java|


<br></br>


##개발목표
-------------------


<br></br>
![Imgur](http://i.imgur.com/P2p4bQI.jpg)


#### 악보 인식 및 해석

영상처리를 통해 실제 악보의 정보를 해석하여 박자 및 음계를 구분한다.

#### 직관적 정보의 이해

사용자가 재구성된 시각 정보를 통해 음계와 박자에 대한 이해를 할 수 있어야 한다.

#### 실제 피아노 건반과의 일치성

실제 건반 위에 보조적인 가상 장치(마커)를 설치하여 사용자로 하여금 정확한 타이밍과 특정 건반을 알 수 있게 한다.




<br></br>



##개발내용
-------------

#### 시스템 구성도

<br></br>

![Imgur](http://i.imgur.com/JSBO9G2.jpg)

악보를 선택하고 머리에 쓰고 이용하게 되면 손으로 UI를 조작할 수 없기 때문에 자이로 센서로 조작을 입력받는다. 악보인식 부분은 Open CV를 이용하여 악보 이미지를 분석 후 데이터 셋을 만드는 라이브러리 파일(Jar file)을 생성한다. 생성된 라이브러리 파일을 Unity에서 플러그인으로 이용할 수 있다.


<br></br>

#### 악보 인식 흐름

<br></br>

![Imgur](http://i.imgur.com/SBfMrFi.jpg)



![Imgur](http://i.imgur.com/anEgZJh.jpg)


악보 이미지 파일에서 불필요한 데이터를 지워내기 위해 영상을 이진화한 후, 음표를 인식하기 위해 오선과 음표를 분할한다. 분할된 음표는 개별로 인식하여 박자를 구분한다. 분리된 오선의 위치에 따라 음계가 결정되므로 각 음표마다 오선의 위치에 따른 음계를 구분한다.

<br></br>

#### 음표 인식

<br></br>

![Imgur](http://i.imgur.com/g3sT2FN.jpg)

음표를 판단하는 기준은 음표의 가운데 줄기가 된다. 이 줄기의 위치와 머리 부분의 위치를 기준으로 음계를 파악하며, 머리 부분의 양 옆, 줄기 부분의 양 옆, 위, 아래 부분을 검사하여 몇 박자인지 구분한다.



<br></br>


##시연영상
-------------


영상 주소
[https://www.youtube.com/watch?v=KlqsGw-KUgA]
[https://youtu.be/c4jTGvZLmoA]


