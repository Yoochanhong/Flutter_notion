<h3>final과 const?</h3>



변하는 수, 변수와는 다르게 값이 고정되는 상수는 dart에서 final과 const라는 키워드를 붙여서 선언한다. 

<img src='https://postfiles.pstatic.net/MjAyMjExMTJfMTYg/MDAxNjY4MTgyMTE2NjQz.-k8bR7MxDSvzO7-t1Ejd48UjcOOc7n1ntTWPPHfqD9kg.3VD48CnJ8GIXcCSjXoCmcAoxi838Ad-L3dE1qumPk8Mg.PNG.chanhongy6/%EC%8A%A4%ED%81%AC%EB%A6%B0%EC%83%B7_2022-11-12_%EC%98%A4%EC%A0%84_12.43.19.png?type=w966'/>  

타입을 굳이 지정하지 않아도 var처럼 타입을 추론해서 넣어주는 것 같다.

<img src='https://postfiles.pstatic.net/MjAyMjExMTJfMjQ2/MDAxNjY4MTgyMTI1NTYx.58yBqqy9hJaQcz5Aqo2Xt9yx4jxpjbA_fh0Uhvr1svMg.eXfKxtsc1Iack96Eu7LrPQ8dZll7-jTutN1Y312XVnog.PNG.chanhongy6/%EC%8A%A4%ED%81%AC%EB%A6%B0%EC%83%B7_2022-11-12_%EC%98%A4%EC%A0%84_12.47.25.png?type=w966'/> 

상수는 값을 한번 넣으면 다른 값을 넣을 수 없다. 넣으면 빨간줄이 뜨면서 에러가 난다.

<img src='https://postfiles.pstatic.net/MjAyMjExMTJfMjY0/MDAxNjY4MTgyMTIxMzkz.kyApuFjrC6X9L9P6B1DfjjSa_1oBXoK8snMNSVh5VT4g.C_BDQtpmu3ZQq9yVT1nO-Sc_ykeg6wgW3OQkWz-qVeIg.PNG.chanhongy6/%EC%8A%A4%ED%81%AC%EB%A6%B0%EC%83%B7_2022-11-12_%EC%98%A4%EC%A0%84_12.44.21.png?type=w966'/> 

이렇게 보면 final과 const는 차이가 없는것 같지만, 무시할 수 없는 차이가 하나 숨겨져 있다.

<img src='https://postfiles.pstatic.net/MjAyMjExMTJfMjM4/MDAxNjY4MTgyMjE1MTEx.s5NX6NfRD_Tz1pKV99P6a5YRIE4rmI5gfFnshJpJKnIg.QoZ0V0u73Snz5cKheUWjCPzNxyBB3ninVnecEKiRJv0g.PNG.chanhongy6/%EC%8A%A4%ED%81%AC%EB%A6%B0%EC%83%B7_2022-11-12_%EC%98%A4%EC%A0%84_12.56.36.png?type=w966'/>  

final은 초기화를 안해도 문제가 없는데 const는 왜 에러가 뜰까?

차이점은 언제 상수로 설정을 해주는지 시점이 조금 다르다.

final은 런타임할때 값이 결정되고, const는 컴파일할때 값이 결정된다.

런타임이 언제일지는 모르지만 컴파일하면서 값이 없는 const는 에러가 뜨는 것이다.

예시로 런타임시점의 시간을 출력해주는 Datetime.now()를 이용해보았다.

<img src='https://postfiles.pstatic.net/MjAyMjExMTJfNzIg/MDAxNjY4MTgyMzczNjQw.R7s1fIYiHmj-h0mWIqljgl28x-B-zFqI-U0UC_VUAZ0g.lWnLuSQRmNcan_RFw1eXTXjU-HrEh1mIyunPND07-44g.PNG.chanhongy6/%EC%8A%A4%ED%81%AC%EB%A6%B0%EC%83%B7_2022-11-12_%EC%98%A4%EC%A0%84_12.59.23.png?type=w966'/> 

런타임할때 값이 결정되는 final과는 다르게 consts는 컴파일했을때 이미 값이 정해져서 DateTime.now()를 사용할 수 없다.

그래서 const는 보통 우리가 아는 진짜 상수(고유명사, 원주율...)를 선언할때 주로 사용하고,

final은 const 역할뿐만 아니라 인스턴스를 담을때도 사용한다.

<h6>*인스턴스: 클래스에서 생성된 객체</h6>