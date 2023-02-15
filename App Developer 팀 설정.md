# Apple Developer 팀 설정하기

<img width="1010" alt="image" src="https://user-images.githubusercontent.com/76683388/218959555-d09ce14c-e4cb-4653-9983-814301a03419.png">

- Apple Developer 페이지를 연 후 Account를 누릅니다.

<img width="983" alt="image" src="https://user-images.githubusercontent.com/76683388/218959778-52757475-1b9f-4cf3-9998-42254dc4c6c7.png">

- 중앙 부분에 인증서를 클릭!
  
<img width="1259" alt="스크린샷 2023-02-15 오후 4 24 42" src="https://user-images.githubusercontent.com/76683388/218963261-2d5b3949-dbd0-487a-9dc2-e89a7332e30c.png">

- Certificates 옆에 있는 + 버튼을 눌러줍니다.
- 
<img width="1242" alt="스크린샷 2023-02-15 오후 4 25 29" src="https://user-images.githubusercontent.com/76683388/218963354-124066db-afd5-474f-a068-bd6fd88df052.png">

- Certificate를 많이 등록하면 저처럼 제한이 되기도 하는데 해결 방법에 대해선 아래에서 다시 설명하겠습니다.

- Apple Development 또는 iOS App Development 를 클릭해주고 Continue를 눌러줍니다.

<img width="1182" alt="스크린샷 2023-02-15 오후 4 26 53" src="https://user-images.githubusercontent.com/76683388/218963496-57522d3f-732a-407a-97ef-d4df3484355c.png">

- 그러면 다음과 같은 화면이 뜰텐데, 여기서 잠시 멈춰줍니다.

<img width="1326" alt="스크린샷 2023-02-15 오후 4 27 47" src="https://user-images.githubusercontent.com/76683388/218963779-b143225d-26d3-4d73-bbf4-97585a45679c.png">

- 맥북에서 키체인 접근을 찾아서 들어가준 후, 사진의 흐름대로 진행하면 됩니다.

<img width="235" alt="스크린샷 2023-02-15 오후 4 27 59" src="https://user-images.githubusercontent.com/76683388/218963833-9ffad6c4-52b8-4815-a36c-a2e8452e8ae7.png">

<img width="506" alt="스크린샷 2023-02-15 오후 4 28 19" src="https://user-images.githubusercontent.com/76683388/218963885-c382eba3-6de7-42d8-9484-015ab610a839.png">

<img width="613" alt="스크린샷 2023-02-15 오후 4 28 41" src="https://user-images.githubusercontent.com/76683388/218963969-16e158a0-32f4-4f23-8f30-f02a4d058c09.png">

- 이렇게 저장을 하게되면 certSigningRequest 파일이 생성되는데 다시 멈춰뒀던 Cerificate로 넘어가서 추가를 해줍니다.
  
<img width="1065" alt="스크린샷 2023-02-15 오후 4 30 23" src="https://user-images.githubusercontent.com/76683388/218964269-93c12b09-2b0b-4d7e-89cf-3fe209b00b49.png">

- 기본적으로 자신의 Certificate는 등록이 되어있기에 팀원들의 인증서를 받아서 등록해주면 됩니다.

- 만들어진 Certificate를 다운로드 해주고, 인증서를 제공한 팀원에게 Certificate를 보내줍시다.

<img width="1322" alt="스크린샷 2023-02-15 오후 4 46 03" src="https://user-images.githubusercontent.com/76683388/218964676-f10567e7-ff5c-4d91-a6a5-5740323cc9c1.png">

- (팀원들이 해야할 행동) 받은 .cer 파일을 키체인에 등록을 해줘야하는데요. 기본적으로 다운로드를 받으면 자동으로 저장되게 됩니다.
- 내 인증서에 들어가서 팀원의 인증서가 없다면 인증서 목록으로 가줍니다.

<img width="952" alt="스크린샷 2023-02-15 오후 4 47 35" src="https://user-images.githubusercontent.com/76683388/218964882-6d9ab0f9-b401-469f-9de2-e203d1c71ed7.png">

- 이런 식으로 하위목록이 있는 인증서만이 유효하더라구요. 하위목록이 없으면 다시 처음부터 CSR 파일을 받고 Certificate를 줘야합니다.
  
<img width="1002" alt="스크린샷 2023-02-15 오후 4 34 05" src="https://user-images.githubusercontent.com/76683388/218964940-7b34ed18-b9b6-4b26-9daf-5c1d6f94a175.png">

- Identifiers 에 들어가서 + 버튼을 눌러줍니다.

<img width="1253" alt="스크린샷 2023-02-15 오후 4 34 31" src="https://user-images.githubusercontent.com/76683388/218965003-1c67b1d1-ba71-4e9a-a3a8-d9c80309d5b8.png">

- Continue
  
<img width="1298" alt="스크린샷 2023-02-15 오후 4 34 34" src="https://user-images.githubusercontent.com/76683388/218965072-f86a60a1-b77c-41ad-be91-b2cb62232aef.png">

- Continue

<img width="1239" alt="스크린샷 2023-02-15 오후 4 34 46" src="https://user-images.githubusercontent.com/76683388/218965150-9c2b2dd3-4ec1-4ee4-8bcc-b6d1a582afa5.png">

- 저는 Firebase 를 사용했기에, Firebase에서 등록했던 Bundle ID를 적어준 후 Continue를 눌러줍니다.

<img width="763" alt="스크린샷 2023-02-15 오후 4 36 10" src="https://user-images.githubusercontent.com/76683388/218965265-16f286a8-a46b-495c-b758-1a984a43b5ab.png">

- 이렇게 완성된 것을 볼 수 있습니다.

- 이제 Profiles 에 들어가서 + 버튼을 눌러줍니다.

<img width="1211" alt="스크린샷 2023-02-15 오후 4 36 34" src="https://user-images.githubusercontent.com/76683388/218965462-88c8d0e1-e6ad-4c8a-bfda-bbafcf334d08.png">

<img width="1242" alt="스크린샷 2023-02-15 오후 4 36 48" src="https://user-images.githubusercontent.com/76683388/218965521-7101a2ed-4e35-4dc7-8d39-e1cf2e4c88bb.png">

<img width="1236" alt="스크린샷 2023-02-15 오후 4 36 55" src="https://user-images.githubusercontent.com/76683388/218965647-01cd2d37-ea52-4b5c-880f-d5f60ceecffe.png">

<img width="1263" alt="스크린샷 2023-02-15 오후 4 36 58" src="https://user-images.githubusercontent.com/76683388/218965726-07c49c2e-1ad3-452e-890f-0bad9bd51460.png">

- 팀원들도 자신의 기기로 직접 테스트하고 싶다면 Devices에 들어가서 팀원들의 기기 ID를 모두 추가한 후에 넣어주면 됩니다.

<img width="1149" alt="스크린샷 2023-02-15 오후 4 37 04" src="https://user-images.githubusercontent.com/76683388/218965808-a9874ac4-e828-4b08-8b5f-5d3db550f89c.png">

- 프로필의 이름을 지정해주면 완료가 됩니다.

<img width="1271" alt="스크린샷 2023-02-15 오후 4 38 01" src="https://user-images.githubusercontent.com/76683388/218965926-17526a0c-48e0-4c16-a485-13c03e20f851.png">

- 완성된 프로필을 다운로드한 후에 Xcode에 등록해줍니다.

<img width="1013" alt="스크린샷 2023-02-15 오후 4 39 02" src="https://user-images.githubusercontent.com/76683388/218966070-3d1ca798-e4c1-464b-868b-58f5360123aa.png">

<img width="994" alt="스크린샷 2023-02-15 오후 4 39 33" src="https://user-images.githubusercontent.com/76683388/218966157-1f50e3df-8f77-4147-99c7-f19e0093c387.png">

- 기본적으로 Automatically manage Signing이 되어있을텐데 이것을 풀어준 후 Provisioning Profile에 아까 다운로드 받은 프로필을 넣어주면 끝입니다.


### Maximum number of certificates generated 문제 해결
- iOS Developer와 App Developer 한명씩 등록을 했는데 문제가 발생해서 더이상 등록을 할 수가 없더라구요.
- 이 해결법은 한명만 딱 더 추가해야할 때 유용한 방법입니다.

<img width="251" alt="스크린샷 2023-02-15 오후 4 56 35" src="https://user-images.githubusercontent.com/76683388/218966932-dbc4142f-5c4f-44b0-b671-6528ca81bd4b.png">

- Xcode Setting에 들어가줍니다.

<img width="830" alt="스크린샷 2023-02-15 오후 4 56 46" src="https://user-images.githubusercontent.com/76683388/218967073-8fe0e930-0aad-4125-aa03-6d2d9790ebd4.png">

- 해당 앱을 제작하는 팀을 클릭해준 후 Manage Certificates를 클릭해줍니다.

<img width="836" alt="스크린샷 2023-02-15 오후 4 56 59" src="https://user-images.githubusercontent.com/76683388/218967305-5874c9c2-3419-46db-9f20-7a4af8592bce.png">

- 이런 비슷한 화면이 나올텐데 추가를 해주시면 자신의 Certificate가 추가가 됩니다.
- Profile에 가서 다시 프로필을 다운받고 import 해주면 끝~!!!