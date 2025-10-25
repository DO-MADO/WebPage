# 💻 On-Premise Full-Stack Deployment & Operations Automation
클라우드 없이 사내 온프레미스 서버에 React/Node.js 기반 웹 서비스를 구축하고,<br>Nginx, PM2, Certbot을 활용해 배포·보안·모니터링을 자동화한 DevOps 파이프라인 프로젝트입니다.



  <a href="https://parkgeonhoportfolio.notion.site/25431721b589818aa9def9eb605cdac7"><img src="https://img.shields.io/badge/노션상세보기-ADFF2F?logo=notion&logoColor=000000&style=flat" 
         alt="Notion Portfolio" height="40" style="margin: 0 10px;"/></a>

<br>

## 📑 프로젝트 요약



- 기간 : 2025.08.01 - 2025.08.13
- 인원 : 1명
- 설명 : 사내 온프레미스 환경에서 React(정적 SPA) 와 Node/Express(API) 기반의 웹 서비스를 구축했습니다.
1.0 버전에서는 Nginx·Certbot·PM2·Deploy Key를 활용해 배포·보안·모니터링을 자동화하여
안정적인 HTTPS 서비스와 반복 가능한 자동 배포 체계를 확립했습니다.

- 2.0 버전에서는 다국어(한/영) 및 다크모드 토글, 관리자 전용 로그인·데이터 관리 페이지,
JWT(HMAC, crypto) 인증 시스템, Multer 기반 이미지 업로드 및 Express 정적 서빙 구조를 추가했습니다.
또한, Base64 → URL 업로드 방식 전환, Nginx proxy_pass 기반 자산 서빙,
세션 상태 유지 및 관리자 인증 보안 강화 등 실서비스 수준의 기능을 구현했습니다.

<br>



## 🧑🏻‍💻 담당 역할

1. **프론트엔드 구축** : React + Vite + Tailwind로 반응형 SPA 구현, 글로벌 UI 컴포넌트 정리

1. **백엔드/API 보안 설계** : Express /api/contact 구현, validator/sanitize-html(message만), 헤더 인젝션 차단, rate-limit, CORS 화이트리스트

1. **메일 전달성 설계** : 하이웍스 SMTPS 465 연동, from=회사계정 + replyTo=사용자로 DMARC 정렬 확보, 오류 처리/로그화

1. **온프레미스 서버 구축** : Ubuntu Server 설치, 무선 LAN 드라이버 오프라인 설치·netplan 권한 수정, 기본 유틸 세팅

1. **방화벽/접근 제어** : UFW로 80/443/SSH 최소 허용, 내부 백엔드 포트 비공개화

1. **리버스 프록시·네트워크 설계** : 공유기 포트포워딩(80/443→A서버), Nginx 도메인 기반 라우팅으로 기존 서비스와 동시 운영

1. **Nginx 설정 개선 & vhost 로그 분리** : WebSocket 업그레이드 매핑(map) 적용, aim/seyeon 서버블록 분리, vhost별 access/error 로그 경로 지정, ACME 인증 경로 우선 처리, SPA 정적/리버스 프록시 구성

1. **HTTPS 적용** : Certbot으로 SSL 발급·HTTP→HTTPS 리다이렉트, 자동갱신 점검

1. **배포 자동화** : GitHub Deploy Key(읽기 전용) + ~/.ssh/config 별칭, deploy.sh로 빌드 → Nginx → SSL → PM2 일괄 배포

1. **배포 스크립트 고도화·운영 관리** : 멱등성 확보, 배포 후 헬스체크(curl) 절차, PM2 프로세스 관리 정책 정리, logrotate(회전/압축/보관일) 구성, vnstat 활성화, 크론으로 매일 03:00 로그 백업 & 7일 보관

1. **모니터링/관측** : Nginx access/error 로그 분리, 실시간 tail 파이프라인, htop/iftop 기반 리소스/네트워크 관측

1. **tmux 3분할 모니터링 스크립트** : htop / iftop / 서비스 로그 세로 균등 3분할, even-vertical 레이아웃, 접속 시 자동 실행

1. **트러블슈팅·문서화** : DNS A레코드 불일치, Nginx proxy_pass 슬래시, .env 미로딩, CORS 미허용 도메인 등 이슈 해결 및 운영 가이드/PPT 작성


<br>

## 🧑🏻‍💻 직접 사용한 기술

| 구분 | 기술 |
| :--- | :--- |
| 🎨 **Frontend** | ![JavaScript](https://img.shields.io/badge/JavaScript-F7DF1E?style=for-the-badge&logo=javascript&logoColor=white) ![React](https://img.shields.io/badge/React-61DAFB?style=for-the-badge&logo=react&logoColor=white) ![Vite](https://img.shields.io/badge/Vite-646CFF?style=for-the-badge&logo=vite&logoColor=white) ![TailwindCSS](https://img.shields.io/badge/TailwindCSS-06B6D4?style=for-the-badge&logo=tailwindcss&logoColor=white) ![Axios](https://img.shields.io/badge/Axios-5A29E4?style=for-the-badge&logo=axios&logoColor=white) ![Sonner](https://img.shields.io/badge/Sonner-1E293B?style=for-the-badge&logo=react&logoColor=white) |
| ⚙️ **Backend / API** | ![Node.js](https://img.shields.io/badge/Node.js-339933?style=for-the-badge&logo=nodedotjs&logoColor=white) ![Express](https://img.shields.io/badge/Express-000000?style=for-the-badge&logo=express&logoColor=white) ![JWT(HMAC)](https://img.shields.io/badge/JWT%20(HMAC)-000000?style=for-the-badge&logo=jsonwebtokens&logoColor=white) ![Multer](https://img.shields.io/badge/Multer-FF6F00?style=for-the-badge&logo=node.js&logoColor=white) ![Nodemailer](https://img.shields.io/badge/Nodemailer-007396?style=for-the-badge&logo=gmail&logoColor=white) ![Validator](https://img.shields.io/badge/Validator.js-000000?style=for-the-badge&logo=javascript&logoColor=white) ![sanitize-html](https://img.shields.io/badge/Sanitize--HTML-5A29E4?style=for-the-badge&logo=javascript&logoColor=white) ![CORS](https://img.shields.io/badge/CORS-FF6F00?style=for-the-badge&logo=securityscorecard&logoColor=white) ![Rate-Limit](https://img.shields.io/badge/Express%20Rate%20Limit-2B037A?style=for-the-badge&logo=express&logoColor=white) ![dotenv](https://img.shields.io/badge/dotenv-000000?style=for-the-badge&logo=dotenv&logoColor=white) |
| 🛠️ **DevOps / Infra** | ![Ubuntu Server](https://img.shields.io/badge/Ubuntu%20Server-E95420?style=for-the-badge&logo=ubuntu&logoColor=white) ![Nginx](https://img.shields.io/badge/Nginx-009639?style=for-the-badge&logo=nginx&logoColor=white) ![Certbot](https://img.shields.io/badge/Certbot-003A70?style=for-the-badge&logo=letsencrypt&logoColor=white) ![PM2](https://img.shields.io/badge/PM2-2B037A?style=for-the-badge&logo=pm2&logoColor=white) ![GitHub](https://img.shields.io/badge/GitHub%20Deploy%20Key-181717?style=for-the-badge&logo=github&logoColor=white) ![SSH](https://img.shields.io/badge/SSH-2C2D72?style=for-the-badge&logo=openssh&logoColor=white) ![UFW](https://img.shields.io/badge/UFW-F05032?style=for-the-badge&logo=linux&logoColor=white) ![Port Forwarding](https://img.shields.io/badge/Port%20Forwarding-0069B4?style=for-the-badge&logo=ethernet&logoColor=white) ![Reverse Proxy](https://img.shields.io/badge/Reverse%20Proxy-009639?style=for-the-badge&logo=nginx&logoColor=white) |
| 📊 **Monitoring / Logging** | ![tmux](https://img.shields.io/badge/tmux-1BB91F?style=for-the-badge&logo=tmux&logoColor=white) ![htop](https://img.shields.io/badge/htop-00BFA5?style=for-the-badge&logo=linux&logoColor=white) ![iftop](https://img.shields.io/badge/iftop-007396?style=for-the-badge&logo=linux&logoColor=white) ![logrotate](https://img.shields.io/badge/logrotate-555555?style=for-the-badge&logo=linux&logoColor=white) ![vnstat](https://img.shields.io/badge/vnstat-004B87?style=for-the-badge&logo=linux&logoColor=white) ![crontab](https://img.shields.io/badge/crontab-5A29E4?style=for-the-badge&logo=linux&logoColor=white) |


<br>


## 🚀 개선 및 확장 기능 (2.0 ver)
1️⃣ 한/영 + 다크모드 토글 추가
- 웹사이트 전역에 언어(한/영) 전환과 테마(다크/라이트) 전환 기능을 추가했습니다.
- 초기 접속 시 언어 선택 모달이 표시되며, 헤더 영역에서 언제든 모드를 변경할 수 있습니다.
  
2️⃣ 라이트모드 UI 개선
- 모바일 환경에서 플로팅 메뉴(☰) 위치와 여백 문제를 해결했습니다.
- 메뉴 투명도 및 색상 톤을 다크모드와 통일하여 일관성 있는 디자인을 구현했습니다.
- 메인 영역의 영상과 콘텐츠 여백 문제를 수정했습니다.
  
3️⃣ 관리자 로그인 및 상태 유지
- 관리자 전용 로그인 페이지를 추가했습니다.
- 로그인 후 새로고침해도 세션이 유지되도록 인증 상태 저장 기능을 구현했습니다.
- 관리자 계정으로 접속 시 제품·프로젝트 데이터를 직접 생성, 수정, 삭제할 수 있습니다.
  
4️⃣ JWT 인증 보안 적용
- 로그인 시 JWT 토큰을 발급받아 API 요청 시 인증 헤더로 전달하는 구조를 도입했습니다.
- 관리자만 제품/프로젝트 데이터 수정이 가능하도록 보안 레벨을 강화했습니다.
- 서버 측에서는 토큰 검증 미들웨어로 안전한 요청만 처리하도록 개선했습니다.
  
5️⃣ Base64 업로드 → URL 방식 변경
- 기존 Base64 문자열로 이미지를 저장하던 구조를 서버 업로드 기반(URL 방식)으로 전환했습니다.
- multer를 활용하여 이미지를 /uploads 폴더에 저장하고, URL로 불러오는 구조를 구축했습니다.
- 로드 중 미리보기·에러 처리·진행 상태 표시 기능을 추가했습니다.
  
6️⃣ 배포 환경 이미지 서빙 설정
- 로컬 환경에서만 동작하던 이미지 업로드 기능을 배포 환경에서도 정상 작동하도록 개선했습니다.
- Nginx 프록시 설정과 .env 환경 변수 구성을 수정하여 서버 간 경로 불일치를 해결했습니다.
  
7️⃣ Nginx 권한 문제 해결
- 배포 환경에서 /uploads 경로의 파일 접근 시 발생하던 404/403 오류를 해결했습니다.
- Nginx의 alias 대신 proxy_pass 방식을 사용해 Node.js 서버를 통해 파일을 서빙하도록 수정했습니다.
- 파일 접근 권한 문제(유저 권한 불일치)를 해결하여 이미지 로딩이 정상화되었습니다.

<br>

## 🖼️ 이미지 자료 2.0 ver
<img width="1435" height="779" alt="스크린샷 2025-10-25 오후 11 20 21" src="https://github.com/user-attachments/assets/a4215778-071c-416d-a693-6746d3d2c4e0" />

<img width="1443" height="793" alt="스크린샷 2025-10-25 오후 10 01 22" src="https://github.com/user-attachments/assets/f796cf0a-0774-49d4-ac07-0f2338057233" />

<img width="1436" height="785" alt="스크린샷 2025-10-25 오후 10 01 37" src="https://github.com/user-attachments/assets/dc77fe39-af36-42a9-a02f-abaa71ac1f45" />

<img width="1440" height="784" alt="스크린샷 2025-10-25 오후 10 01 47" src="https://github.com/user-attachments/assets/f9271455-0b63-4c02-ae94-4e891f39c244" />

<img width="1920" height="300" alt="제목을 입력해주세요  (1)" src="https://github.com/user-attachments/assets/f2c0870d-b9f2-4d91-ad67-afdb63fffd55" />


<img width="1869" height="741" alt="KakaoTalk_Photo_2025-10-25-23-03-55 004" src="https://github.com/user-attachments/assets/c720dc58-19b8-4285-b03f-47a1b1600460" />

<img width="1857" height="897" alt="KakaoTalk_Photo_2025-10-25-23-03-55 006" src="https://github.com/user-attachments/assets/f97c916e-967f-446b-b9a4-4bd252c142b5" />

<img width="1866" height="1166" alt="KakaoTalk_Photo_2025-10-25-23-03-54 001" src="https://github.com/user-attachments/assets/eb5a9c9e-a8ef-4743-8a8b-0b3e1f2b26b0" />

<img width="1663" height="747" alt="KakaoTalk_Photo_2025-10-25-23-03-55 002" src="https://github.com/user-attachments/assets/8ac62ff9-baf3-4044-a799-b49311cae707" />



<br>

## 🖼️ 이미지 자료 1.0 ver

![003](https://github.com/user-attachments/assets/3741dca3-8c55-4ccb-95fd-f93ed6ed9b66)
![004](https://github.com/user-attachments/assets/cfa2dab6-3601-4881-b42c-fd1fd284b596)
<img width="6000" height="3375" alt="005" src="https://github.com/user-attachments/assets/1b7bcdb0-8dfd-4784-8e83-132bbde5a33d" />
![006](https://github.com/user-attachments/assets/68303e79-4952-4048-b680-675fb5f5d642)
![007](https://github.com/user-attachments/assets/3903740a-6219-48c7-8812-fa03db14355a)
![012](https://github.com/user-attachments/assets/8427b241-54ee-4658-ba67-6ebbfdb97581)
![013](https://github.com/user-attachments/assets/72f2d33a-160f-4b60-97bd-08d16ff5628c)
![014](https://github.com/user-attachments/assets/59e0f09b-c0f5-4db3-b35f-73b7fcd4c01a)
![015](https://github.com/user-attachments/assets/01b763d5-605e-4500-b52a-d6debdbac87b)
![016](https://github.com/user-attachments/assets/89c479fc-cf5c-4cba-aca7-6b116be8c46a)
![017](https://github.com/user-attachments/assets/a9bbf732-f4f7-4d35-8bd7-9c685a75a77c)
![018](https://github.com/user-attachments/assets/2450a693-cf9c-4102-ad82-715b0d6bbe4f)
![019](https://github.com/user-attachments/assets/612d5561-ebc4-47c6-8343-061fd419b376)
![020](https://github.com/user-attachments/assets/e0d25c01-6977-4161-b0b7-63b36f196dcc)
![021](https://github.com/user-attachments/assets/c2fece8b-9ad9-46d4-912e-53db4187bdcd)
![022](https://github.com/user-attachments/assets/6379ecb9-cb31-4244-9317-d90eb87b5cf0)
![023](https://github.com/user-attachments/assets/7c879c2a-c2b9-43bb-afbd-c194bcf859fe)
![024](https://github.com/user-attachments/assets/da5ab243-a7ee-49aa-9520-2f68f23f1494)
![025](https://github.com/user-attachments/assets/89a9c89b-5fbe-4da4-9573-708f6c093a1b)
![026](https://github.com/user-attachments/assets/0ea35ba5-2469-477e-a4e8-09fc89362eb2)
![027](https://github.com/user-attachments/assets/68f28005-2da5-48e6-808e-2a55ad01b1d5)
