# 🚍 버스왔수다
![image](https://github.com/user-attachments/assets/f296fff9-0fee-4754-8543-bf34401b352d)

![image](https://github.com/user-attachments/assets/d88aeaaf-0405-4d17-a40f-c48ab5e20ee3)

##### 🏆 구름톤 11기 대상 작품

### 📜 Contents
 1. [Overview](#-overview)
 2. [서비스 화면](#-서비스-화면)
 3. [주요 기능](#-주요-기능)
 4. [개발 환경](#%EF%B8%8F-개발-환경)
 5. [시스템 아키텍처](#-시스템-아키텍처)
 6. [기술 특이점](#-기술-특이점)
 7. [기획 및 설계 산출물](#-기획-및-설계-산출물)
 8. [Conventions](#-conventions)
 9. [팀원 소개](#-팀원-소개)
 
## ✨ Overview
##### 🏆 개발 기간: 24.10.30 ~ 24.11.01 
> 

## ✨ 버스왔수다의 배포 사이트
##### 🏆 [사이트](https://k983be54c0935a.user-app.krampoline.com/home)


## 👀 서비스 화면
### ✨ `웹 / 모바일(아이폰 12 Pro 기준 max-width:480px)` 지원O

### 로그인 화면
<div>
  <img src="https://github.com/user-attachments/assets/f1b9122d-6fa8-4507-a796-3e66bc8ebe07" width="40%"/>
</div>

### 버스 목록 화면 
<div>
  <img src="https://github.com/user-attachments/assets/86ffa671-a605-427c-aa79-ba9f2d7acef6" width="40%"/>
</div>

### 버스 신청 화면
<div>
  <img src="https://github.com/user-attachments/assets/ced3d3ed-46b4-44ed-9afc-b32ae30568f0" width="30%"/>
	  <img src="" width="10%"/>
  <img src="https://github.com/user-attachments/assets/1b7a6727-ad8d-422d-b721-b22c280f4a5d" width="30%"/>
</div>

### 즐겨찾기 화면
<div>
  <img src="https://github.com/user-attachments/assets/5e140b89-12d4-4707-b2f1-0572cf6643ed" width="40%"/>
</div>

  
## ✨  기능 

- `회원 관리`
	- 회원가입, 로그인, 비밀번호 찾기, 비밀번호 변경, 이메일 변경, 아이디 찾기 등의 기능을 제공하여 사용자의 계정을 효율적으로 관리합니다.
	- Spring Security와 세션을 사용하여 구현했습니다.
	- 마이페이지에서는 회원 탈퇴 및 프로필 사진을 변경할 수 있는 기능을 제공했습니다.


- `이메일 인증`
    - 회원가입 시 이메일로 비밀번호가 전송되며, 사용자는 해당 비밀번호를 입력하여 회원가입을 완료할 수 있습니다.
	- 이메일 전송은 **JavaMailSender**를 사용하여 처리되며, 마이페이지에서 이메일을 변경할 때도 동일한 방식으로 인증을 요구합니다. 인증을 완료하지 않으면 서비스 이용이 제한됩니다.


- `소셜 로그인`
	- OAuth 2.0을 사용하여 네이버, 카카오 소셜 로그인을 구현했습니다.
	- 소셜 로그인 시 사용자의 이메일 정보를 확인하고, 중복된 이메일이 있을 경우 중복 알림을 제공하여 계정 혼동을 방지합니다.
	- 기존 회원과 소셜 로그인 회원을 동일하게 관리하기 위해 DB에 소셜 로그인 필드를 추가하고, 로그인 처리 로직을 커스터마이징했습니다.


- `커뮤니티 관리 및 Quill API 도입`
	- 게시글과 댓글의 CRUD(Create, Read, Update, Delete) 구현했습니다. 또한 AJAX를 활용한 공감을 자유롭게 표시할 수 있습니다.
	- 글 작성 시 Quill API를 도입하여 사용자가 다양한 텍스트 스타일을 적용할 수 있는 WYSIWYG 에디터 기능을 제공했습니다. 이를 통해 텍스트의 포맷팅, 이미지 삽입, 하이퍼링크 추가 등이 가능합니다.




- `AWS EC2 서버 배포`
	- AWS EC2 프리티어를 사용하여 서버를 배포하였으며
    - 도메인은 가비아에서 구입한 후 Route 53을 사용해 EC2 인스턴스와 연결했습니다. 
    - SSL 인증서를 갱신하여 HTTPS 통신을 적용했습니다.


## 🖥️ 개발 환경

**Management Tool**
- 형상 관리 : Git
- 디자인 : Figma

**🐳 Backend**
- Java `21`
- Spring Framework `3.2.4`
- Swagger `2.6.0`
- Batch `5,x`
- Jpa


**🗝️ API**
- OpenAI
- TMAP API
- GoogleMAP API
- Twilio
- 제주특별자치도 API
  

**🦊 Frontend**
- React
- TypeScript



**🗂️ DB**
- MariaDB

**🌐 Server**
- Kubernetes
- 카카오 크램플린IDE

**🔨 IDE**
- IntellJ `2023.2`
- VSC

## 💫 시스템 아키텍처

![image](https://github.com/user-attachments/assets/c7aef2ff-367f-4697-abac-dbe7ee1caca8)



### [🎨 화면 설계서](https://www.figma.com/design/xCP8rQaX7zpOIl7bsej1Tw/%EA%B5%AC%EB%A6%84%ED%86%A4?node-id=0-1&node-type=canvas&t=7EZXaZ8RmmOBFJqb-0)

![image](https://github.com/user-attachments/assets/b995f3db-04ba-4c56-a952-d6e5e02734ea)


### [✨ ER Diagram]()
![image](https://github.com/user-attachments/assets/df1f10d7-2971-4305-b85e-78fbb630e1a2)



# 💞 팀원 소개
##### ❤️‍🔥 FEELBUDDY를 개발한 `피로그래밍 21기` 팀원들을 소개합니다!

| **[황영은]()** | **[서장호]()** | **[엄석훈](https://github.com/SeokhunEom)** | **[이윤신](https://github.com/TransparentDeveloper)** | **[최승호](https://github.com/chltmdgh522)** |
| :---------------------------------------------------------------------------------------------------------------------------: | :---------------------------------------------------------------------------------------------------------------------------: | :---------------------------------------------------------------------------------------------------------------------------: | :---------------------------------------------------------------------------------------------------------------------------: | :---------------------------------------------------------------------------------------------------------------------------: |
| <img src="https://github.com/user-attachments/assets/7f6428b7-e110-40ed-98b1-be6e595c9f79" width="400"> | <img src="https://github.com/user-attachments/assets/c420a1a8-b268-45e4-9703-25d122a57a9d
" width="400"> | <img src="https://github.com/user-attachments/assets/aec44d20-60ee-4411-9a6f-8dba81ff5403" width="400"> | <img src="https://github.com/user-attachments/assets/c221d4c4-54f2-4230-a175-56c26358309f
" width="400"> |  <img src="https://github.com/user-attachments/assets/e792dfc6-e2a7-4b42-b5a5-27672d4df6c7" width="400"> |
| Leader & Planner | Designer | Frontend |  Frontend |   Backend |




## 😃 팀원 역할

- **황영은**
  - 팀장, 기획, 발표, 피피티 제작
- **서장호**
  - 워크플로우 설계, 와이어 프레임 설계 
- **엄석훈**
  - UI 개발 및 API 연동 
- **이윤신**
  - UI 개발 및 API 연동 
- **최승호**
  - API 개발, 서버 배포

