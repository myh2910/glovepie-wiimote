# glovepie-wiimote

[한국어](./README.ko.md) | [영어](./README.md)

Windows에서 닌텐도 Wii 리모컨으로 게임하기.

## 설치

1. 다음 파일들을 내려받아 압축을 푼다.
   - <https://github.com/elitak/PPJoy/releases/download/v0.8.4.6/PPJoySetup-0.8.4.6.zip>
   - <https://github.com/Ravbug/GlovePIE/releases/download/Release/GlovePIE-0.43.zip>
1. 컴퓨터가 테스트 모드로 실행되지 않은 경우, `bcdedit -set TESTSIGNING ON`을
   관리자 권한으로 실행한 뒤 컴퓨터를 재시작한다. 그 다음
   `PPJoySetup-0.8.4.6.exe`를 실행하여 PPJoy 드라이버를 실행시킨다. 새로운 창이
   뜨면 "Add -> Add -> Done" 버튼을 차례로 클릭하여 새로운 조이스틱을 추가한다.  
   ![Test mode](assets/test-mode.png)  
   화면 하단 모서리에 이러한 워터마크가 뜰 텐데, PPJoy 드라이버를 실행하려면
   어쩔 수 없는 것이므로 만약 없애려면 관리자 권한으로
   `bcdedit -set TESTSIGNING OFF`를 실행하고 컴퓨터를 재시작한다.

## 실행

1. 블루투스를 킨 다음 Windows 제어판을 켜서 "하드웨어 및 소리" 밑에 있는 "장치
   추가"를 클릭한 뒤, 장치가 인식될 때까지 Wii 리모컨의 <kbd>1</kbd>과
   <kbd>2</kbd> 버튼을 동시에 누른다. Wii 리모컨이 인식되면 "Cancel -> Cancel"
   버튼을 차례로 클릭하여 필요한 파일을 설치한다.
1. `GlovePIE.exe` 파일을 실행한 다음 "File -> Open" 버튼을 차례로 클릭하여
   실행하고자 하는 `*.PIE` 스크립트를 연 뒤, "Run" 버튼을 클릭하여 스크립트를
   실행시킨다. 이제 GlovePIE가 실행되는 동안 Wii 리모컨으로 게임이 가능하다.
1. 게임이 끝난 다음 GlovePIE의 "Stop" 버튼을 클릭하여 스크립트를 중단한 뒤 Wii
   리모컨과의 블루투스 연결을 해제한다.

## GlovePIE 스크립트

다음은 GlovePIE 스크립트 예시다. 자세한 건
[GlovePIE 위키](https://github.com/Ravbug/GlovePIE/wiki)<sup>([Syntax](https://github.com/Ravbug/GlovePIE/wiki/GlovePIE-Scripts-and-Syntax), [Wiimote](<https://github.com/Ravbug/GlovePIE/wiki/Wiimote-(Nintendo-Wii-Remote)>), [PPJoy](https://github.com/Ravbug/GlovePIE/wiki/Joysticks,-PPJoy,-and-Kinect#ppjoy))</sup>를
참조.

```rust
PPJoy.Analog0 = Smooth(MapRange(Wiimote.SmoothPitch, -80, 80, -1, 1))
PPJoy.Digital0 = Wiimote.Up
PPJoy.Digital1 = Wiimote.Down
PPJoy.Digital2 = Wiimote.Left
PPJoy.Digital3 = Wiimote.Right
PPJoy.Digital4 = Wiimote.A
PPJoy.Digital5 = Wiimote.B
PPJoy.Digital6 = Wiimote.Minus
PPJoy.Digital7 = Wiimote.Plus
PPJoy.Digital8 = Wiimote.Home
PPJoy.Digital9 = Wiimote.One
PPJoy.Digital10 = Wiimote.Two
```

## 유로 트럭 시뮬레이터 2 설정

스티어링 강도는 높게, 스티어링 비선형은 낮게 설정한다. 아래는 키 & 버튼의
설정이다.

| 기능                          | 키보드           | Wii 리모컨       | Wii 리모컨 & 눈차크 |
| ----------------------------- | ---------------- | ---------------- | ------------------- |
| 가속                          | <kbd>W</kbd>     | <kbd>Right</kbd> | <kbd>C</kbd>        |
| 브레이크 / 후진               | <kbd>S</kbd>     | <kbd>Left</kbd>  | <kbd>Z</kbd>        |
| 스티어링 좌측                 | <kbd>A</kbd>     | <kbd>Up</kbd>    |                     |
| 스티어링 우측                 | <kbd>D</kbd>     | <kbd>Down</kbd>  |                     |
| 엔진 시동/정지                | <kbd>E</kbd>     | <kbd>B</kbd>     | <kbd>+</kbd>        |
| 주차 브레이크                 | <kbd>Space</kbd> |                  | <kbd>-</kbd>        |
| 왼쪽 방향지시등               | <kbd>[</kbd>     | <kbd>1</kbd>     | <kbd>Joy Down</kbd> |
| 오른쪽 방향지시등             | <kbd>]</kbd>     | <kbd>2</kbd>     | <kbd>Joy Up</kbd>   |
| 라이트                        | <kbd>L</kbd>     | <kbd>-</kbd>     | <kbd>2</kbd>        |
| 경적                          | <kbd>H</kbd>     | <kbd>A</kbd>     | <kbd>A</kbd>        |
| 와이퍼                        | <kbd>P</kbd>     | <kbd>+</kbd>     | <kbd>1</kbd>        |
| 실행                          | <kbd>Enter</kbd> | <kbd>Home</kbd>  | <kbd>Home</kbd>     |
| 경로 관리자 네비게이션 페이지 | <kbd>F5</kbd>    |                  | <kbd>Down</kbd>     |
| 경로 관리자 진단 페이지       | <kbd>F7</kbd>    |                  | <kbd>Up</kbd>       |

## 링크

- [PPJoy](https://github.com/elitak/PPJoy)
- [GlovePIE](https://github.com/Ravbug/GlovePIE)
- [관련 유튜브 영상](https://www.youtube.com/watch?v=QH6h2dO_eYY)
- [관련 네이버 포스트](https://m.blog.naver.com/truecg/10154582210)
