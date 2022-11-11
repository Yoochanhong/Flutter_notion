<h3>var와 dynamic의 차이점</h3>



dart는 타입추론을 지원한다. var라는 키워드를 통해 쓸 수 있다.

<img src = 'https://postfiles.pstatic.net/MjAyMjExMTFfMjQ5/MDAxNjY4MTc3OTE3MDM2.cmvEsEnl5tXHFBv86qXtr5R5C9-9D0LoZ-VpD-78xK0g.LTo1_AUlL-3dc1YFRRWo7rgBrWYbr2rTr-XfNZyiNxUg.PNG.chanhongy6/%EC%8A%A4%ED%81%AC%EB%A6%B0%EC%83%B7_2022-11-11_%EC%98%A4%ED%9B%84_11.39.49.png?type=w966'/> 

String으로 선언한 변수에는 문자형밖에 들어 갈 수 없지만, var로 선언하면 dart에서 타입을 자동으로 추론해준다.

var intValue = 14; 처럼 선언해도 가능하다.

<img src = 'https://postfiles.pstatic.net/MjAyMjExMTFfNzIg/MDAxNjY4MTc3OTI0NDA1.6KcIVM2nmlxIHQp1UHyync-qj1EynRZMAFx8f8glZ-Ug.WO00x73KLLP8ZniOqvDQA8LqO99THqT94Wloi1jCpxkg.PNG.chanhongy6/%EC%8A%A4%ED%81%AC%EB%A6%B0%EC%83%B7_2022-11-11_%EC%98%A4%ED%9B%84_11.40.18.png?type=w966'/> 

하지만 한번 선언한 var 변수는 다른 타입의 값을 넣으면 오류가 생긴다.

<img src='https://postfiles.pstatic.net/MjAyMjExMTFfNTgg/MDAxNjY4MTc4MzU0OTg3.dT1Zg-ojfjCt6yCZuFj-SwenUvEU9ZgzuZzejwyxVeYg.qGXwIeeXVaPTXZAgzCIVBt60LYWiPONhqIn_9YuVW7og.PNG.chanhongy6/%EC%8A%A4%ED%81%AC%EB%A6%B0%EC%83%B7_2022-11-11_%EC%98%A4%ED%9B%84_11.52.06.png?type=w966'/>

정수형 값은 문자형 변수에 할당할 수 없다고 오류 메시지를 보내준다.

<img src='https://postfiles.pstatic.net/MjAyMjExMTFfMTkg/MDAxNjY4MTc3OTI5NzA3.0QGJ3bDo4XqroC93EwOFWUc6KLQNVaPzhOgwcAcr_scg.2vM9P6na4tKbWcdw7Cr72qqdh1tDH2ZaLvZiASCOk04g.PNG.chanhongy6/%EC%8A%A4%ED%81%AC%EB%A6%B0%EC%83%B7_2022-11-11_%EC%98%A4%ED%9B%84_11.42.30.png?type=w966'/> 

이와 다르게 dynamic 변수는 한번 선언한 후에도 다른 타입을 넣어줄 수 있다.