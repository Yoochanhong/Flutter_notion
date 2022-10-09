<h3>your app is missing support for the following URL schemes</h3>


맥북에서 구글 로그인 만들다가 튕길 때

ios 폴더 우클릭 -> 맨 밑에 Flutter -> Open iOS module in Xcode 클릭

<img src="https://postfiles.pstatic.net/MjAyMjEwMDlfMzIg/MDAxNjY1MzIxODMxMTUz.ML4iF5RLadV5GwBuO6EJ02NyDTD-wyNZ98MtTxL2qcEg.J9bgljKPVucPkj7oa70WDlNeB4yCj8HTnhoNyA7B9Awg.PNG.chanhongy6/%EC%8A%A4%ED%81%AC%EB%A6%B0%EC%83%B7_2022-10-09_%EC%98%A4%ED%9B%84_10.17.17.png?type=w966"/>

Runner -> GoogleService-info -> REVERSED_CLIENT_ID value 복사하기

<img src = "https://postfiles.pstatic.net/MjAyMjEwMDlfMTk1/MDAxNjY1MzIyMjYwMzEx.eoaC078BplOY-pQlLBPVs2tuahHFFBZiHQk1qfcBxwMg.kkHxYNZgfwR3KFN4ff3wNBaB_g9Mnh1wIZvZ6wU-Vw0g.PNG.chanhongy6/%EC%8A%A4%ED%81%AC%EB%A6%B0%EC%83%B7_2022-10-09_%EC%98%A4%ED%9B%84_10.25.49.png?type=w966"/>

Runner -> Info -> URL Types 클릭 -> URL Schemes에 붙여넣기

<img src = "https://postfiles.pstatic.net/MjAyMjEwMDlfMjA4/MDAxNjY1MzIyNzgxNDY0.hO2srYqIkThb1cZjjbDildtrgCFTaRk4xLW01o3l08kg.yloF3QFTuCWyliArdHDDPKZO64Lc73c5zJ7c1JE-lCAg.PNG.chanhongy6/%EC%8A%A4%ED%81%AC%EB%A6%B0%EC%83%B7_2022-10-09_%EC%98%A4%ED%9B%84_10.36.42.png?type=w966"/>

저장 후 다시 빌드해보면 오류가 해결된다.

<img src = "https://postfiles.pstatic.net/MjAyMjEwMDlfMzkg/MDAxNjY1MzIyOTIyMjky.aBak0F7WO8BER2nyyvrH-3svTbp_AMf8pszECBOtOWIg.Zo0kaUM1HH_Pb_fwHxS3BVcpxH_MvY5XF-XJJrIdQoUg.PNG.chanhongy6/%EC%8A%A4%ED%81%AC%EB%A6%B0%EC%83%B7_2022-10-09_%EC%98%A4%ED%9B%84_10.41.09.png?type=w966"/>