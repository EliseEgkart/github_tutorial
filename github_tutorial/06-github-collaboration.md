# GitHub 협업 기능

GitHub를 활용한 협업 방식은 크게 두 가지 상황으로 나눌 수 있다.

1. 오픈소스 프로젝트에 기여하는 경우  
2. 같은 레포지토리 안에서 팀이 함께 개발하는 경우  

각 상황은 협업 구조와 작업 흐름이 다르기 때문에,  
아래에서는 **실제 사용 흐름과 화면 예시를 중심으로 단계별로 설명**한다.

---

## 1. Open Source 기여의 관점 (Fork 기반 협업)

오픈소스 프로젝트는 외부 기여자가 원본 저장소에 직접 코드를 올릴 수 없도록 관리되는 경우가 대부분이다.  
따라서 기여자는 원본 저장소를 복사한 뒤, 그 복사본에서 작업하고 Pull Request를 통해 변경 사항을 제안하는 방식으로 협업한다.

전체적인 흐름은 다음과 같다.

Fork 생성 → Fork한 레포를 로컬로 Clone → 브랜치에서 작업 → commit / push  
→ 원본 레포(upstream)에 Pull Request 생성

---

### 1-1. Fork 생성
![alt text](/img/git-open-colabo-01.png)

기여하고 싶은 오픈소스 레포지토리에 접속한 뒤 Fork 버튼을 누른다.  
이 과정은 원본 레포를 **내 계정 또는 조직 소유의 레포로 복사**하는 작업이다.

이후의 모든 작업은 이 Fork된 레포에서 이루어지며,  
원본 레포는 그대로 유지된다.

---

### 1-2. Fork한 레포를 로컬로 Clone
![alt text](/img/git-open-colabo-02.png)

Fork가 완료되면, 내 계정에 생성된 레포지토리에서 Clone URL을 복사하여 로컬 환경으로 내려받는다.  
이때 로컬 Git 기준에서 `origin`은 **내 Fork 레포**를 가리키게 된다.

원본 레포는 이후 `upstream`이라는 이름으로 추가해 관리하는 경우가 많다.

---

### 1-3. 로컬에서 작업 후 commit / push
![alt text](/img/git-open-colabo-03.png)

로컬 환경에서 기능 추가나 버그 수정을 진행한 뒤,  
변경 사항을 커밋하고 내 Fork 레포로 push한다.

이 단계까지는 원본 레포에는 아무런 변화가 없으며,  
모든 변경은 내 Fork에만 반영된다.

push가 완료되면 GitHub 화면에서 Pull Request 버튼이 활성화된다.  
이를 통해 내 Fork의 변경 내용을 원본 레포에 반영해 달라는 요청을 보낸다.

---

### 1-4. Pull Request 생성 (Upstream으로 기여 요청)
![alt text](/img/git-open-colabo-04.png)

Pull Request에는 단순히 코드 변경뿐만 아니라  
변경 이유, 배경, 확인해야 할 사항 등을 함께 작성하게 되며,  
이 과정에서 리뷰와 토론이 이루어진다.

---

## 2. GitHub를 사용한 협업의 관점 (팀 / 조직 협업)

팀 프로젝트나 조직 협업에서는 보통  
같은 저장소 안에서 Issue 단위로 작업을 나누고,  
각 작업을 브랜치와 Pull Request로 관리한다.

전체 흐름은 다음과 같다.

Issue 생성 → Issue에서 브랜치 생성  
→ 로컬에서 브랜치 fetch / checkout  
→ 작업 후 commit / push  
→ Pull Request → 코드 리뷰 → Merge

---

### 2-1. Issue 생성 및 작업 정의
![alt text](/img/git-colabo-01.png)

작업을 시작하기 전에 먼저 Issue를 생성한다.  
Issue에는 작업의 목적, 필요한 변경 사항, 완료 조건 등을 정리해 작성한다.

이 과정을 통해 “무엇을 왜 하는 작업인지”가 팀 전체에 공유된다.  
[99-collaboration-convention-definition.md](99-collaboration-convention-definition.md) <- 컨벤션 정의는 해당 문서에 기술되어있음.

---

### 2-2. Issue에서 브랜치 생성
![alt text](/img/git-colabo-02.png)

Issue 화면에서 Create branch 버튼을 눌러 해당 작업을 위한 브랜치를 생성한다.  
브랜치 이름은 보통 라벨과 이슈 번호를 포함해 작성한다.

예시:  
Feat/6

이렇게 하면 해당 브랜치가 어떤 Issue와 연결된 작업인지 바로 알 수 있다.

---

### 2-3. 로컬에서 브랜치 가져오기
![alt text](/img/git-colabo-03.png)

GitHub에서 안내하는 fetch 및 checkout 명령을 로컬에서 실행한다.  
이를 통해 원격 저장소에 생성된 브랜치 정보를 가져오고,  
실제로 작업할 브랜치로 전환한다.

이 시점부터 해당 브랜치에서 개발을 진행하게 된다.
[99-collaboration-convention-definition.md](99-collaboration-convention-definition.md) <- 컨벤션 정의는 해당 문서에 기술되어있음.
---

### 2-4. 작업 후 commit / push
![alt text](/img/git-colabo-04.png)

코드 수정이 완료되면 현재 브랜치에서 커밋을 생성하고,  
변경 내용을 원격 브랜치로 push한다.

커밋을 남기기 전에는 항상  
현재 브랜치가 올바른지 확인하는 습관이 중요하다.
[99-collaboration-convention-definition.md](99-collaboration-convention-definition.md) <- 컨벤션 정의는 해당 문서에 기술되어있음.

---

### 2-5. Pull Request 작성
![alt text](/img/git-colabo-05.png)

push 이후 Compare & pull request 버튼을 눌러 Pull Request를 생성한다.  
Pull Request에는 제목과 설명을 작성하고,  
리뷰어와 라벨을 지정한다.

이 단계부터 팀원 간의 코드 검토와 의견 교환이 시작된다.

---

### 2-6. 코드 리뷰
![alt text](/img/git-colabo-06.png)

리뷰어는 변경된 코드를 확인한 뒤 의견을 남긴다.  
리뷰는 단순한 승인 절차가 아니라,  
코드 품질을 높이고 실수를 줄이기 위한 과정이다.

Pull Request 작성자는 자신의 PR을 직접 승인할 수 없으며,  
다른 사람이 리뷰를 진행해야 한다.

---

### 2-7. Merge 및 반영 확인
![alt text](/img/git-colabo-07.png)

리뷰가 모두 완료되면 Pull Request를 merge하여  
변경 사항을 main 브랜치에 반영한다.

이후 Pull Request 목록에서 병합 상태를 확인할 수 있으며,  
문제가 발생한 경우 Revert Pull Request를 통해 변경을 되돌릴 수도 있다.
