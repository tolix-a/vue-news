# News.
딥서치 뉴스 API를 이용한 뉴스 앱입니다. <br/>
무료 버전을 이용해 매월 요청 300번까지만 가능합니다.

링크 [📗](https://vue-news-sepia.vercel.app/)

##

### `개발 환경`
<img src='https://img.shields.io/badge/Vue%20js-35495E?style=for-the-badge&logo=vuedotjs&logoColor=4FC08D'> <img src="https://img.shields.io/badge/Sass-CC6699?style=for-the-badge&logo=sass&logoColor=white">
<img src="https://img.shields.io/badge/MongoDB-4EA94B?style=for-the-badge&logo=mongodb&logoColor=white">
<img src="https://img.shields.io/badge/axios-671ddf?&style=for-the-badge&logo=axios&logoColor=white">
<img src="https://img.shields.io/badge/Vercel-000000?style=for-the-badge&logo=vercel&logoColor=white">
<img src="https://img.shields.io/badge/Figma-F24E1E?style=for-the-badge&logo=figma&logoColor=white">
<img src="https://img.shields.io/badge/GIT-E44C30?style=for-the-badge&logo=git&logoColor=white">
<img src="https://img.shields.io/badge/github-181717?style=for-the-badge&logo=github&logoColor=white">
<img src="https://img.shields.io/badge/Postman-FF6C37?style=for-the-badge&logo=Postman&logoColor=white">
<img src="https://img.shields.io/badge/Express%20js-000000?style=for-the-badge&logo=express&logoColor=white">

### `제작 기간`
2024.10.25 - 약 5일

### `기능`
* 검색
- 정치 경제 등 섹션별 분류

### `과정`
1. 구조

- 어느 페이지에서든 검색 가능하고 화면 크기가 줄어들어도 검색창 크기가 너무 작아지지 않게끔 만들기 위해 검색버튼을 헤더에 놓고 토글형식으로 만들었습니다. <br/>
- 검색 후 이전 화면으로 돌아갈 수 있도록 검색 결과 화면에 뒤로가기 버튼을 추가했습니다.
- 섹션별 기사, 검색 결과 기사 수가 많아서 무한 스크롤 기능을 넣고자 했으나 사용하는 API의 요청 한도가 월 300회라는 점을 고려하여 기사를 더 불러오는 기능은 넣지 않았습니다.
- 기사 제목을 클릭하면 기사 내용이 나오도록 제작하고 싶었으나 API에서는 기사 전문이 아닌 summary와 원본 기사 링크가 제공되어 기사를 누르면 해당 기사로 넘어가게 만들었습니다.
- 무료 버전에서는 토픽별 기사를 요청할 수 없었기 때문에 메인 페이지에는 뉴스의 가장 기본적인 섹션이라 생각되는 정치, 경제, 사회, 문화의 기사 몇개씩만 가져왔습니다.

2. 개발
- 익스프레스 서버와 axios를 이용해 데이터를 받고 우선 개발
- 쿼리를 보내서 탭 별로 다른 데이터가 나오도록 구성
- 검색 창을 열어놓고 다른 페이지로 가면 검색 창이 닫히고 초기화하게 만듦
- 요청 횟수 제한 때문에 기사 누르면 새창에서 열리게 함. 

##

### 트러블슈팅
- env를 쓰고부터 요청한 api 데이터가 넘어오지 않는 문제
  - dotenv가 필요하다는 것을 배움


------------
여기다 이미지를 넣을까
