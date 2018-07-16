# wifiart
wifiart 프로젝트는 lazypic 방문객에게 만화를 이용해서
즐겁게 wifi 패스워드를 알려주는 문화입니다.

현대의 와이파이 기기는 대문자, 소문자, 숫자, 특수문자가 들어간 형태의 패스워드 설정을 요구합니다.
방문객이 이 패스워드를 읽고 기억하기 힘들기 때문에 위 조건이 충족되면서 
재미적인 요소가 패스워드 속에 있고, 읽기 편한 패스워드를 구성하려고 노력했습니다.
그래서 lazypic이 생각한 패스워드는 `w!f!5Gworkhard` 입니다. 더 좋은 패스워드 아이디어가 있다면 [issue](https://github.com/lazypic/wifiart/issues)에 남겨주세요.

완성된 만화는 이 리포지터리에 `.svg`, `.png`, `.pdf` 파일로 백업되어집니다.

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
