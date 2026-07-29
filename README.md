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
<img width="3012" height="1424" alt="image" src="https://github.com/user-attachments/assets/e999efcc-1ca1-4357-90a1-840a086bff8f" />
