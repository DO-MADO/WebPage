# 🖥️ React·Node.js 풀스택 웹 서비스 개발과 자동화된 운영·배포 인프라 구축

사내 온프레미스 환경에서 **React SPA + Node.js/Express API** 서비스를 구축하고, **Nginx·PM2·Certbot·deploy.sh** 를<br> 활용해 배포·보안·모니터링이 자동화된 **End-to-End 운영 환경**을 직접 설계한 프로젝트입니다.



<br>



<details>
<summary><h3>📑 프로젝트 요약 (자세히 보기)</h3></summary>
<div markdown="1">
<br>
<a href="https://parkgeonhoportfolio.notion.site/25431721b589818aa9def9eb605cdac7">
  <img 
    src="https://img.shields.io/badge/노션상세보기-FFFFFF?logo=notion&logoColor=000000&style=flat" 
    alt="Notion Portfolio" 
    height="40" 
    style="margin: 0 10px;"
  />
</a>

- **기간** : 2025.08.01 - 2025.08.13
- **인원** : 1명 (기획 · Design · FE · BE · Infra · DevOps 전담)
- **설명** :
  **클라우드 의존 없이** 사내 온프레미스 환경에서 **React(SPA) + Node.js(API)** 기반의 웹 서비스를 구축하고 운영 전반을 설계했습니다.

  **🔹 Ver 1.0 (인프라 & 자동화) :**<br>
  Nginx·Certbot·PM2·Deploy Key를 활용해 **배포·보안·모니터링이 자동화된 DevOps 파이프라인**을 구축했습니다.<br> 또한 메일 서버(DMARC) 연동과 HTTPS 적용을 통해 실서비스 수준의 안정적인 운영 환경을 마련했습니다.<br>

  **🔹 Ver 2.0 (기능 고도화 & 보안) :**<br>
  서비스 가치를 높이기 위해 **JWT(HMAC) 관리자 인증**, **Multer 기반 이미지 업로드(URL 서빙)**, **다국어/다크모드**를 구현했습니다.<br> 아울러 Nginx `proxy_pass`를 활용해 정적 자산 서빙 문제를 해결하고, 세션 유지 로직을 보강하여 사용자 경험(UX)을 대폭 강화했습니다.
<br>
<hr>
</div>
</details>



<br>

## 🌟 주요 기능

### 🎨 1. 사용자 중심의 반응형 SPA & 관리자 시스템
- **React + TailwindCSS** 기반으로 모바일/PC에 최적화된 반응형 UI 및 **다국어(한/영)·다크모드** 지원
- **JWT(HMAC) 인증** 기반의 관리자 대시보드에서 **JSON 파일 기반의 데이터 관리(CRUD)** 기능 구현

### 🛡️ 2. 안정적인 메일/API 서버 & 자산 관리
- **Nodemailer(SMTPS)** 및 **DMARC 보안 정렬**을 적용하여 스팸 분류를 방지한 **메일 전송 시스템** 구축
- **Multer**를 활용해 로컬 파일 시스템에 이미지를 저장하고 **URL 정적 서빙(Static Serving)**으로 처리

### 📡 3. 온프레미스 인프라 & 네트워크 최적화
- **Nginx Reverse Proxy** 구성을 통한 **SSL(HTTPS)** 적용 및 단일 IP 기반 다중 도메인 라우팅
- **UFW 방화벽** 설정 및 내부 백엔드 포트 격리(Private)를 통한 온프레미스 서버 보안 강화

### ⚙️ 4. 배포 자동화 및 무중단 운영 (DevOps)
- **GitHub Deploy Key + deploy.sh**: 빌드·배포·재시작 과정을 원클릭으로 처리하는 **멱등성 배포 파이프라인** 구축
- **PM2 & Observability**: 프로세스 무중단 운영(Auto Restart) 및 **tmux·logrotate** 기반의 실시간 로그·리소스 관제


<br>

## 🏗️ 시스템 아키텍처
<img width="1920" height="1080" alt="_주_Aim-웹_앱-홈페이지-제작-PPT-006" src="https://github.com/user-attachments/assets/1b3c6042-4d7d-474b-bc4a-7c70db36c544" />
<img width="1920" height="1080" alt="_주_Aim-웹_앱-홈페이지-제작-PPT-012" src="https://github.com/user-attachments/assets/d3bd5963-c5e4-4ecf-ad24-94b8e2bacb7f" />
<img width="1920" height="1080" alt="_주_Aim-웹_앱-홈페이지-제작-PPT-014 (1)" src="https://github.com/user-attachments/assets/60853890-6c34-4058-b6aa-ef1b484b07a3" />
<img width="1920" height="1080" alt="(주)Aim 웹_앱 홈페이지 제작 PPT-011" src="https://github.com/user-attachments/assets/8054de4f-736c-49ed-837d-853ad09f0015" />
<img width="1920" height="1080" alt="_주_Aim-웹_앱-홈페이지-제작-PPT-014" src="https://github.com/user-attachments/assets/befefd19-6808-413a-8bc0-c441b76639e9" />

<br>
<br>
<br>

## 🌱 담당 역할 (Ver 1.0)

### 🎨 프론트엔드 개발 및 백엔드 보안
- **FE 구현**: React + Vite + Tailwind 기반 반응형 SPA 구현 및 글로벌 UI 컴포넌트 표준화
- **API 보안**: Express 엔드포인트 구현 및 `validator`·`sanitize-html`·`rate-limit`·`CORS` 적용으로 웹 취약점 차단
- **메일 시스템**: 하이웍스 SMTPS 연동 및 **DMARC(From/Reply-To) 정렬**을 통해 스팸 분류 없는 메일 전달성 확보

### 🏗️ 온프레미스 인프라 (서버 & 네트워크)
- **서버 환경 구축**: Ubuntu Server 설치부터 **무선 LAN 드라이버 오프라인 설치**, Netplan 구성까지 제로 베이스 구축
- **네트워크 설계**: 공유기 포트포워딩(80/443) 및 **Nginx Reverse Proxy** 설계를 통한 단일 IP·다중 도메인 라우팅 구현 
- **보안 및 접근 제어**: **UFW 방화벽**으로 80/443/SSH만 허용하고 내부 백엔드 포트는 외부 격리(Private) 조치
- **HTTPS 보안 적용**: **Certbot**을 활용한 SSL 발급 및 자동 갱신, HTTP → HTTPS 리다이렉트 및 WebSocket 업그레이드 설정

### 🚀 배포 자동화 및 DevOps (CI/CD)
- **배포 파이프라인**: **GitHub Deploy Key**와 `deploy.sh` 쉘 스크립트를 작성하여 **Git Pull → Build → Nginx/PM2 Reload** 원클릭 배포 구현 
- **스크립트 고도화**: 배포 후 **Health Check(curl)** 로직 및 멱등성을 보장하는 스크립트 작성으로 배포 안정성 확보

### 📊 운영 관리 및 모니터링
- **모니터링 및 관제**: **tmux 3분할(htop/iftop/logs)** 관제 스크립트를 작성하여 리소스/네트워크/로그를 한 화면에서 실시간 파악
- **로그 관리 시스템**: **Nginx vhost별 로그 분리** 및 **logrotate** 설정으로 로그 회전/압축/보관(7일) 자동화
- **백업 및 트래픽 분석**: Crontab을 활용해 매일 03:00 시스템/로그 백업 자동화 및 **vnstat** 기반 네트워크 트래픽 분석


<br>
<br>

## 🌳 담당 역할 (Ver 2.0)

### 🎨 프론트엔드 UX 고도화
- **전역 상태 관리**: Context API를 활용하여 전역 **다국어(i18n) 및 다크모드/라이트모드 테마 토글** 시스템 구현
- **반응형 UI 최적화**: 모바일 환경에서의 플로팅 메뉴 레이아웃(Z-index, 여백) 개선 및 **일관된 디자인 시스템** 적용
- **사용자 경험(UX) 개선**: 언어 선택 모달 및 로딩 인디케이터, 에러 피드백 UI를 추가하여 사용자 인터랙션 품질 강화

### 🔐 인증 시스템 및 보안 아키텍처
- **무상태(Stateless) 인증 구현**: **JWT(HMAC)** 기반의 관리자 인증 시스템을 구축하고, **Refresh 없는 세션 유지** 로직 구현 
- **보안 미들웨어 적용**: 서버 측에 토큰 검증 미들웨어를 배치하여 비인가 요청을 원천 차단하고, 관리자 전용 데이터 CRUD 권한 제어
- **관리자 대시보드 구축**: 관리자 전용 페이지를 신설하여 프로젝트/제품 데이터의 생성·수정·삭제(CRUD) 기능 구현

### 👷 구조 개선 및 성능 최적화 (리팩토링)
- **이미지 처리 방식 개선**: 기존 Base64 인코딩 방식의 메모리 비효율 문제를 해결하기 위해 **Multer 업로드 + URL 서빙** 방식으로 아키텍처 전면 교체 
- **정적 자산 최적화**: 이미지 업로드 시 미리보기(Preview) 기능을 추가하고, 로컬/배포 환경 간 경로 불일치를 환경변수(.env)로 표준화

<br>
<br>

## 🧑🏻‍💻 직접 사용한 기술
| 분류 | 기술 스택 |
| :--- | :--- |
| 🎨 **Frontend** | ![JavaScript](https://img.shields.io/badge/JavaScript-F7DF1E?style=for-the-badge&logo=javascript&logoColor=white) ![React](https://img.shields.io/badge/React-61DAFB?style=for-the-badge&logo=react&logoColor=white) ![Vite](https://img.shields.io/badge/Vite-646CFF?style=for-the-badge&logo=vite&logoColor=white) ![TailwindCSS](https://img.shields.io/badge/TailwindCSS-06B6D4?style=for-the-badge&logo=tailwindcss&logoColor=white) ![Axios](https://img.shields.io/badge/Axios-5A29E4?style=for-the-badge&logo=axios&logoColor=white) ![Sonner](https://img.shields.io/badge/Sonner-1E293B?style=for-the-badge&logo=react&logoColor=white) |
| ⚙️ **Backend / API** | ![Node.js](https://img.shields.io/badge/Node.js-339933?style=for-the-badge&logo=nodedotjs&logoColor=white) ![Express](https://img.shields.io/badge/Express-000000?style=for-the-badge&logo=express&logoColor=white) ![JWT(HMAC)](https://img.shields.io/badge/JWT%20(HMAC)-000000?style=for-the-badge&logo=jsonwebtokens&logoColor=white) ![Multer](https://img.shields.io/badge/Multer-FF6F00?style=for-the-badge&logo=node.js&logoColor=white) ![Nodemailer](https://img.shields.io/badge/Nodemailer-007396?style=for-the-badge&logo=gmail&logoColor=white) ![Validator](https://img.shields.io/badge/Validator.js-000000?style=for-the-badge&logo=javascript&logoColor=white) ![sanitize-html](https://img.shields.io/badge/Sanitize--HTML-5A29E4?style=for-the-badge&logo=javascript&logoColor=white) ![CORS](https://img.shields.io/badge/CORS-FF6F00?style=for-the-badge&logo=securityscorecard&logoColor=white) ![Rate-Limit](https://img.shields.io/badge/Express%20Rate%20Limit-2B037A?style=for-the-badge&logo=express&logoColor=white) ![dotenv](https://img.shields.io/badge/dotenv-000000?style=for-the-badge&logo=dotenv&logoColor=white) |
| 🛠️ **DevOps / Infra** | ![Ubuntu Server](https://img.shields.io/badge/Ubuntu%20Server-E95420?style=for-the-badge&logo=ubuntu&logoColor=white) ![Nginx](https://img.shields.io/badge/Nginx-009639?style=for-the-badge&logo=nginx&logoColor=white) ![Certbot](https://img.shields.io/badge/Certbot-003A70?style=for-the-badge&logo=letsencrypt&logoColor=white) ![PM2](https://img.shields.io/badge/PM2-2B037A?style=for-the-badge&logo=pm2&logoColor=white) ![GitHub](https://img.shields.io/badge/GitHub%20Deploy%20Key-181717?style=for-the-badge&logo=github&logoColor=white)  ![Bash Shell](https://img.shields.io/badge/Bash_Shell-4EAA25?style=for-the-badge&logo=gnu-bash&logoColor=white) ![SSH](https://img.shields.io/badge/SSH-2C2D72?style=for-the-badge&logo=openssh&logoColor=white) ![UFW](https://img.shields.io/badge/UFW-F05032?style=for-the-badge&logo=linux&logoColor=white)  |
| 📊 **Monitoring / Logging** | ![tmux](https://img.shields.io/badge/tmux-1BB91F?style=for-the-badge&logo=tmux&logoColor=white) ![htop](https://img.shields.io/badge/htop-00BFA5?style=for-the-badge&logo=linux&logoColor=white) ![iftop](https://img.shields.io/badge/iftop-007396?style=for-the-badge&logo=linux&logoColor=white) ![logrotate](https://img.shields.io/badge/logrotate-555555?style=for-the-badge&logo=linux&logoColor=white) ![vnstat](https://img.shields.io/badge/vnstat-004B87?style=for-the-badge&logo=linux&logoColor=white) ![crontab](https://img.shields.io/badge/crontab-5A29E4?style=for-the-badge&logo=linux&logoColor=white) |


<br>
<br>

## ⚡ Troubleshooting Log (핵심 문제 해결)

### 1️⃣ 단일 공인 IP 환경의 라우팅 충돌 해결 (Ver 1.0)
* **문제**: 사내 공인 IP는 하나인데, 2개의 도메인을 내부망의 각기 다른 서버로 연결해야 하는 상황.
* **해결**: Nginx Reverse Proxy를 활용해 `Host Header`에 따라 트래픽을 분기(Routing) 처리하여 IP 추가 비용 없이 해결.

### 2️⃣ HTTPS 인증서 발급 실패 및 WebSocket 끊김 (Ver 1.0)
* **원인**: Nginx의 'HTTPS 강제 리다이렉트'가 ACME 챌린지 경로보다 우선순위가 높았음.
* **해결**: `location ^~ /.well-known/acme-challenge/` 블록을 최상단에 배치하여 예외 처리하고, WebSocket 업그레이드 헤더 추가.

### 3️⃣ 배포 환경에서의 이미지 권한 오류 (Ver 2.0)
* **문제**: 로컬에선 잘 되던 이미지 업로드가 배포 서버(Ubuntu)에선 403/404 에러 발생.
* **해결**: Nginx `alias` 대신 Node.js 서버로 `proxy_pass` 하여 애플리케이션 레벨에서 파일을 서빙하도록 아키텍처 변경.

<br>
<br>

## 🖼️ 이미지 자료 (2.0 ver)
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
<br>
<br>


## 🖼️ 이미지 자료 (1.0 ver)
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
