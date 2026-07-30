# 개발 워크스테이션 구축

## 1. 개발 환경
- OS: macOS (Apple Silicon, arm64)
- Docker Desktop: 28.4.0
- Docker Server(초기): 27.3.1
- OrbStack: 2.2.1
- CPU: 11 Cores / RAM: 7.6GB

## 2. 작업 진행 내용

### 2-1. Docker 설치 및 확인
- Docker Desktop 28.4.0 설치
- 데몬 정상 작동 확인

### 2-2. Git 저장소 구성
- 작업 폴더 생성: ~/dev-workstation
- git init 으로 저장소 초기화
- README.md 작성 (개발 환경 정보 포함)
- 첫 커밋: 5a0b17d "docs: 개발 환경 정보 README 작성"

### 2-3. GitHub 원격 저장소 연동
- GitHub Public 저장소 생성: dev-workstation
- 원격 저장소 연결 (git remote add origin)
- git push 성공
- 웹에서 README 정상 렌더링 및 커밋 해시 일치 확인

### 2-4. OrbStack 전환
- OrbStack 2.2.1 설치
- 초기 설정에서 Docker 엔진 선택
- docker context 를 orbstack 으로 전환
- docker version 으로 Server 엔진(OrbStack, linux/arm64) 확인

### 2-5. 컨테이너 실행 테스트
- docker run --rm hello-world 실행
- "Hello from Docker!" 메시지 정상 출력 → 구축 완료
- <img width="1506" height="712" alt="Screenshot 2026-07-29 at 4 48 24 PM" src="https://github.com/user-attachments/assets/13b5981e-f819-40c4-8e15-7de4616d96a8" /><img width="757" height="80" alt="Screenshot 2026-07-29 at 4 59 19 PM" src="https://github.com/user-attachments/assets/83bfd62a-19db-410d-b907-1383b3c7e9f1" />

### 2-6. nginx 컨테이너 실습
- docker pull nginx 로 이미지 다운로드
- docker run -d -p 8080:80 --name my-nginx nginx 실행
- localhost:8080 브라우저 접속 → nginx 기본 페이지 확인
- 컨테이너 생명주기 실습 (run → stop → start → rm)
- docker ps / ps -a / logs / images 명령어 숙달
- 이미지(설계도) vs 컨테이너(실행 인스턴스) 개념 이해

<img width="753" height="812" alt="Screenshot 2026-07-30 at 10 56 16 AM" src="https://github.com/user-attachments/assets/20d31cdf-8900-4b4d-87d9-e713a9547fd9" />







### 2-7. .gitignore 설정
- .gitignore 파일 생성
- 불필요한 파일(로그, 임시 파일 등) 추적 제외 설정
- 커밋 및 push 완료

### 2-8. Dockerfile 작성 및 커스텀 이미지 빌드
- Dockerfile 작성 (베이스 이미지: nginx)
- docker build -t my-nginx . 로 커스텀 이미지 빌드 성공
- docker run -d -p 8080:80 my-nginx 로 컨테이너 실행
- localhost:8080 브라우저 접속 → 커스텀 페이지 확인
- 이미지 빌드 → 컨테이너 실행 흐름 이해
