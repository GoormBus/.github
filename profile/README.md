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
 6. [Conventions](#-conventions)
 7. [팀원 소개](#-팀원-소개)
 
## ✨ Overview
##### 🏆 개발 기간: 24.10.30 ~ 24.11.01 
> 
제주도에서는 대중교통 이용이 어려운 어르신들이 많습니다. 복지카드는 발급받았지만, 배차 간격이 길고 버스가 부족하여 실제 이용에 불편함을 겪고 계십니다. 또한, 스마트기기 사용이 익숙하지 않은 어르신들에게 실시간 버스 도착 정보를 확인하는 일은 쉽지 않습니다. 그래서 저희 '버스왔수다' 프로젝트는 디지털 기기 사용에 어려움을 겪는 어르신들을 위해 처음부터 끝까지 음성으로 이용할 수 있는 '제주도 버스 도착 알림 콜 서비스'를 개발했습니다.

 
## ✨ PDF
##### 🏆 [사이트](https://drive.google.com/file/d/1Orha-Acf9v_-QSNIj74_-2CDK5P66Hvs/view?usp=sharing)


## ✨ 버스왔수다의 배포 사이트
##### 🏆 [사이트](https://k983be54c0935a.user-app.krampoline.com/home)


## 👀 서비스 화면
### ✨ `웹 / 모바일(아이폰 12 Pro 기준 max-width:480px)` 지원O

### 영상
https://youtu.be/alaCbBrBfkw?si=eE8uGLCQfWd0xlWV

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

### 버스 전화 화면
https://youtu.be/hhftesjkh94?si=sEchlAs4iuC-TM2X

### 즐겨찾기 화면
<div>
  <img src="https://github.com/user-attachments/assets/5e140b89-12d4-4707-b2f1-0572cf6643ed" width="40%"/>
</div>

  
## ✨ 기능 

- `회원 관리`
	- 어르신들이 쉽게 사용할 수 있도록 회원가입과 로그인을 동시에 진행할 수 있게 구현했습니다. 인증은 전화번호를 통해 간편하게 이루어지며, 인증 완료 시 JWT 토큰을 발급하여 사용자 인증을 처리합니다.


- `음성 인식 및 Open AI 활용`
  	- 출발지와 도착지를 직접 입력하거나 음성으로 입력할 수 있습니다. 음성 입력 시, Open AI를 통해 더 정확한 키워드를 추출하여 반영합니다.

- `티맵 API를 통한 거리 확인`
	- 출발지와 도착지를 기준으로 티맵 API를 사용해 거리를 계산하고, 이에 가장 가까운 버스 정류장을 찾아 추천합니다. 이 정류장의 노선 ID와 정류장 ID는 백엔드로 전달됩니다.

- `제주 실시간 버스 API 스케줄링`
	- 프론트엔드로부터 받은 데이터를 제주 실시간 버스정보 API로 10초마다 전송하여 출발지로부터 남은 정류장 수를 실시간으로 확인합니다. 사용자가 "5정류장 남음" 알림을 요청한 경우, 남은 정류장이 5개일 때 Twilio API를 통해 사용자에게 전화 알림이 가며, 이때 반복하여 총 2번의 알림 전화가 발송됩니다.

- `즐겨찾기 및 알림 기능`
	- 검색한 버스 기록은 즐겨찾기에 추가할 수 있어 이후에 편리하게 조회할 수 있습니다. 알림은 스케줄링을 통해 지정된 시간대에 반복 알림이 설정되며, 예를 들어, 사용자가 오후 3시경 기록을 남기면 이후 매일 오후 3시경 두 차례 알림 전화가 발송됩니다. 알림 기능은 사용자가 원할 때 비활성화할 수 있습니다.


- `Crampin IDE를 활용한 Kubernetes 배포`
	- 카카오에서 제공하는 Crampin IDE를 이용해 프론트엔드, 백엔드, 데이터베이스를 순차적으로 빌드하고, Kubernetes에 배포하기 위해 Cargo를 통해 배포 작업을 수행했습니다.

## 🖥️ 개발 환경

**Management Tool**
- 형상 관리 : Git
- 디자인 : Figma

**🐳 Backend**
- Java `21`
- Spring Framework `3.2.4`
- Swagger `2.6.0`
- Jpa
- Scheduler


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
##### ❤️‍🔥 버스왔수다를 개발한 `구름톤 11기` 팀원들을 소개합니다!

| **[황영은](https://github.com/)** | **[서장호](https://github.com/)** | **[엄석훈](https://github.com/SeokhunEom)** | **[이윤신](https://github.com/TransparentDeveloper)** | **[최승호](https://github.com/chltmdgh522)** |
| :---------------------------------------------------------------------------------------------------------------------------: | :---------------------------------------------------------------------------------------------------------------------------: | :---------------------------------------------------------------------------------------------------------------------------: | :---------------------------------------------------------------------------------------------------------------------------: | :---------------------------------------------------------------------------------------------------------------------------: |
| <img src="https://github.com/user-attachments/assets/157338aa-355d-4c97-b5b9-35e0acd6b113" width="400"> | <img src="https://github.com/user-attachments/assets/c420a1a8-b268-45e4-9703-25d122a57a9d" width="400"> | <img src="https://github.com/user-attachments/assets/173e4414-7238-407a-aaa4-68fe2b436a7a" width="400"> | <img src="https://github.com/user-attachments/assets/c221d4c4-54f2-4230-a175-56c26358309f" width="400"> |  <img src="https://github.com/user-attachments/assets/e792dfc6-e2a7-4b42-b5a5-27672d4df6c7" width="400"> |
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

