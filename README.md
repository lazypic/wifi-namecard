# wifiart
wifi 패스워드를 알려주는 만화.

시나리오

```
1. 손님이 Lazypic을 방문합니다.
2. 손님 "여기 Wifi 패스워드가 뭐예요?"
3. Lazypic은 손님에게 벽에 붙혀있는 4컷 만화를 손으로 가리킵니다.
4. 손님은 벽에 붙은 만화를 읽고, Wifi 패스워드를 설정합니다.
```

현대의 와이파이 기기는 대문자, 소문자, 숫자, 특수문자가 들어간 형태의 패스워드 설정을 요구합니다.
방문객이 랜덤한 패스워드를 읽고 기억하기 힘들기 때문에 위 조건이 충족되면서 
재미 요소가 패스워드 속에 있고, 읽기 편한 패스워드를 구성하려고 노력했습니다.
그래서 lazypic 이 생각한 패스워드는 `w!f!5Gworkhard` 입니다. 더 좋은 패스워드 아이디어가 있다면 [issue](https://github.com/lazypic/wifiart/issues)에 남겨주세요.

완성된 만화는 이 리포지터리에 `.svg`, `.png`, `.pdf` 파일로 백업되어집니다.
백업된 이미지는 필요시 A4용지에 인쇄해서 사용합니다.

![wifiart](wifi_art.png "Wifi Art")

#### 작업에 사용된 유틸리티
- convert : 스캔이미지를 bmp로 변환하기 위해서 사용했습니다.

```bash
$ convert scanimage.png scanimage.bmp
```

- potrace : bmp 이미지를 vector로 변환하기 위해서 사용했습니다.

```bash
$ potrace --svg scanimage.bmp -o scanimage.svg -k 0.8
```

- svg를 편집하기 위해서 [iVinci Express](https://itunes.apple.com/kr/app/ivinci-express/id607900811?mt=12)를 사용했습니다. macOS에서 가볍게 svg파일을 수정하기 편리한 툴입니다.

- qlmanage : svg 편집이후 인쇄를 위해 인쇄해상도에 해당하는 bitmap 변경. A4 300dpi에 해당하는 픽셀수는 2480x3508 입니다.

```bash
$ qlmanage -t -s 3508 -o . scanimage.svg
```
