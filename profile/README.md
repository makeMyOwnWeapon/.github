# Learn On Air

크래프톤정글 4기 나만의무기 프로젝트 입니다.

## 목차

- [프로젝트 개요](#프로젝트-개요)
- [주요 기능](#주요-기능)
- [기술 스택](#기술-스택)
- [아키텍처](#아키텍처)
- [도전 과제 및 해결 방법](#도전-과제-및-해결-방법)
- [성과](#성과)
- [설치 및 실행](#설치-및-실행)
- [포스터](#포스터)

## 프로젝트 개요

온라인 강의의 다음과 같은 단점을 보완하기 위해 만들어진 프로젝트 입니다.
- 높은 자유도로 인해 집중력이 떨어집니다.
- 강의 이해에 대한 객관적 측정이 힘듭니다.


## 주요 기능

- **문제 출제**: AI를 활용해 문제를 제공하여 강의 집중력을 향상시킵니다.
- **졸음 및 자리이탈 감지**: 사용자의 졸음 및 자리이탈을 감지하여 잠을 깨우고, 자동으로 강의를 멈춥니다.
- **레포트 제공**: 학습시간 통계, 문제 다시보기, 추천 복습 키워드 제공 등으로 사용자의 학습을 돕습니다.
- 더 많은 기능들은 [여기](#)에서 확인할 수 있습니다.

## 기술 스택

- **프론트엔드**
<img src="https://img.shields.io/badge/react-61DAFB?style=for-the-badge&logo=react&logoColor=black">

- **백엔드**
<img src="https://img.shields.io/badge/node.js-339933?style=for-the-badge&logo=Node.js&logoColor=white">
<img src="https://img.shields.io/badge/nest.js-E0234E?style=for-the-badge&logo=nestjs&logoColor=white">

- **데이터베이스**
<img src="https://img.shields.io/badge/mysql-4479A1?style=for-the-badge&logo=mysql&logoColor=white"> 
- **버전 관리**
<img src="https://img.shields.io/badge/github-181717?style=for-the-badge&logo=github&logoColor=white">

- **CI/CD**: []
- **기타 도구**: [ AWS, ]

## 아키텍처
<img width="711" alt="스크린샷 2024-05-23 오후 7 59 29" src="https://github.com/kts5927/test/assets/154499036/752c9070-184d-4e18-8e2d-0b5a08fb8c2f">

이 프로젝트는 다음과 같은 아키텍처를 따릅니다: (예시, 수정 필요)

- **클라이언트-서버 구조**: 프론트엔드와 백엔드가 명확히 분리되어 있어 유지보수가 용이합니다.
- **마이크로서비스**: 각 서비스가 독립적으로 배포 및 확장 가능합니다.
- **RESTful API**: 클라이언트와 서버 간 통신을 위한 RESTful API를 설계하였습니다.
- **데이터베이스 설계**: 데이터베이스는 관계형/비관계형 데이터베이스를 사용하여 최적의 성능을 발휘하도록 설계되었습니다.

## 도전 과제 및 해결 방법

### 도전 과제 1: 크롬 익스텐션 보안 문제
<img width="685" alt="스크린샷 2024-05-23 오후 8 29 38" src="https://github.com/kts5927/test/assets/154499036/ca440631-f57d-41c8-9743-f3e0d72cf9f7">


**설명**
- Learn On Air 프로그램은 사용자의 얼굴을 인식해 졸음과 자리비움을 감지하는 기능이 있습니다.
- 그래서 익스텐션 기능에 MediaPipe라는 AI 프로그램을 사용하여 기능을 추가하고자 하였습니다.
- 하지만 크롬 익스텐션에서는 MediaPipe를 사용할 경우, CSP 에러가 발생하였습니다.

**해결 방법**
- 브라우저에는 MediaPipe를 제외한 촬영 기능만 남겨두었습니다.
- MediaPipe는 Nest.js 백엔드 서버에 추가하는 것으로 문제를 해결하였습니다.

### 도전 과제 2: 과도한 CPU 사용
<img width="687" alt="스크린샷 2024-05-23 오후 8 29 50" src="https://github.com/kts5927/test/assets/154499036/03004894-9ed2-48d2-9c02-8f824abed38c">

**설명**
- MediaPipe를 백엔드 서버로 보내자, 과도한 CPU 사용과 느린 영상 처리 속도는 문제가 되었습니다.
- 이로 인해 Nest 백엔드 서버는 느린 응답속도, 그리고 적은 인원 수용이라는 문제점이 발생하였습니다.

**해결 방법**:
- 별도의 영상처리 서버를 만들어서 MediaPipe를 실행하였습니다.
- 이로인해 MediaPipe서버는 영상처리만, Nest 서버는 응답 처리만 할 수 있게 되었습니다.

## 성과
<img width="689" alt="스크린샷 2024-05-23 오후 8 30 30" src="https://github.com/kts5927/test/assets/154499036/327d5a67-6cd0-4939-ab24-666b7a8758db">


**성능향상** 
- 이로 인해 응답시간은 1120ms에서 52ms로(약 4% 수준) 빨라졌습니다.
- 사용자는 최대 2명에서 100명까지 수용 가능해졌습니다.(50배)

## 포스터
<img width="689" src="https://github.com/makeMyOwnWeapon/.github/assets/144863392/2f4bd947-45e4-460d-815d-a98290c3f1ba">

## 팀원소개
[김동욱]([http://zeldahagoshipda.com](https://github.com/UkdongKim))

