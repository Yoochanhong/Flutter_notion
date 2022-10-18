<h3>minSdkVersion 에러

안드로이드 실기기에 빌드하려고 하는 중이였다.

<img src='https://postfiles.pstatic.net/MjAyMjEwMThfMjAg/MDAxNjY2MDkyMTMwNTU4.oMZK0-a5-JZMSoLRxfQ-sOy2RJkoW3DfzQdjdFWwYZYg.z95IQtgzbSNdVvWW_zYV7s3mJk7-WU7Sf4d13X0c4AUg.PNG.chanhongy6/%EC%8A%A4%ED%81%AC%EB%A6%B0%EC%83%B7_2022-10-18_%EC%98%A4%ED%9B%84_8.14.49.png?type=w966' width = 1000px height = 250px/>

플러터의 안드로이드 폴더로 들어가서 sdk 버젼을 바꿔라...라는것 같다.

<img src = 'https://postfiles.pstatic.net/MjAyMjEwMThfMjc3/MDAxNjY2MDkyNDkyNzkw.NFWz_PCJWXXZn2i3SscxvEHaUy-ljBuApudt-GNslx4g.eSN01bghpg_DDM7wd3OvQvt0HiMr7CvWSHbQanMGtggg.PNG.chanhongy6/%EC%8A%A4%ED%81%AC%EB%A6%B0%EC%83%B7_2022-10-18_%EC%98%A4%ED%9B%84_8.15.22.png?type=w966' width = 900px/> 

Android >> app >> build.gradle로 들어간다.

❗️꼭 app 안쪽에 있는 build.gradle로 들어가야 한다.❗️

<img src="https://postfiles.pstatic.net/MjAyMjEwMThfOTIg/MDAxNjY2MDkyNDk5MDc4.6zakhDi_qyFds-lWBkZ0Ft9HHHpCUGAdCgrimacA578g.Npt0_WIqppyiyqwWH3WrgK1E-_2ld3GsogeKKxhZyAQg.PNG.chanhongy6/%EC%8A%A4%ED%81%AC%EB%A6%B0%EC%83%B7_2022-10-18_%EC%98%A4%ED%9B%84_8.15.32.png?type=w966" width = 900px/> 

flutter.minSdkVersion을 21로 고쳐주면 잘 해결된다.