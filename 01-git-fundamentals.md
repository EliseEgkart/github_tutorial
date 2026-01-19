# Git 기본 개념

## Git과 GitHub에 대하여
![Git flow](img/git-flow.png)

### Git이란?
Git은 소스 코드의 변경 이력을 체계적으로 관리하기 위한 **분산 버전 관리 시스템(DVCS)** 이다.  
파일이 언제, 왜, 어떻게 변경되었는지를 **커밋(commit) 단위**로 기록하며, 각 개발자는 자신의 로컬 환경에서 독립적으로 브랜치를 생성·수정·실험할 수 있다.

중앙 서버에 의존하지 않고도 모든 변경 이력을 보존할 수 있기 때문에,  
협업 과정에서 충돌을 최소화하고 안정적으로 개발 흐름을 관리하는 데 핵심적인 역할을 한다.

---

### GitHub란?
GitHub는 Git 저장소를 온라인에서 호스팅하고 **협업을 지원하는 플랫폼 서비스**이다.  
원격 저장소를 통해 코드 공유, 이슈 관리, 코드 리뷰(Pull Request), 프로젝트 문서화, CI 연동 등  
팀 개발에 필요한 기능을 통합적으로 제공한다.

단순한 코드 보관소를 넘어,  
**오픈소스 협업**, **개발자 포트폴리오**, **프로젝트 관리의 중심 허브**로 활용된다.

---

### Git과 GitHub의 관계 정리
- **Git**은 버전 관리를 수행하는 도구이고  
- **GitHub**는 Git 저장소를 공유하고 협업을 돕는 플랫폼이다.

Git은 GitHub 없이도 사용할 수 있지만,  
GitHub는 Git을 기반으로 동작한다.

👉 서로 다른 개념이므로, 차이를 명확히 이해하고 사용하는 것이 중요하다.

---

## Git, GitHub에서 사용되는 어휘 정리
더 자세한 내용은 [03-commit-history.md](03-commit-history.md)에서 다룬다.  
여기서는 **어휘와 개념 이해**에 초점을 맞춘다.

![Git repository](img/git-repository.webp)

### repository (repo)란?
Repository는 프로젝트의 파일과 **변경 이력**을 함께 관리하는 저장 공간이다.  
소스 코드뿐 아니라 문서, 설정 파일, 커밋 기록까지 모두 하나의 repository 단위로 관리된다.

Git에는 다음 두 종류의 저장소가 존재한다.
- **로컬 저장소(Local Repository)**  
- **원격 저장소(Remote Repository)**

---

### local repository란?
Local repository는 **개발자의 컴퓨터에 존재하는 Git 저장소**이다.  
파일 수정, 커밋 생성 등 대부분의 작업은 로컬 저장소에서 이루어진다.

---

### remote repository란?
Remote repository는 **인터넷 상에 존재하는 저장소**로,  
여러 개발자가 코드를 공유하고 협업하기 위해 사용된다.

GitHub는 대표적인 원격 저장소 제공 서비스이다.

---

![Git working area](img/git-working-area.webp)

### add란?
Add는 **작업 디렉토리에서 변경된 파일을 커밋 대상으로 선택하는 단계**이다.  
수정된 파일 중 어떤 변경을 기록할지 Git에게 알려주는 역할을 하며,  
선택된 파일들은 **스테이징 영역(Staging Area)** 에 올라간다.

```sh
git add file.txt
git add .
```

---

### commit이란?
Commit은 파일의 변경 사항을 하나의 기록 단위로 저장하는 작업이다.
각 커밋은 “무엇을 왜 변경했는지”를 나타내는 스냅샷 역할을 하며,
프로젝트의 변경 이력을 시간 순서대로 추적할 수 있게 한다.
```sh
git commit -m "Add initial files"
```
---

### push란?
Push는 로컬 저장소의 커밋을 원격 저장소로 업로드하는 작업이다.
자신의 변경 사항을 다른 사람들과 공유할 때 사용된다.
```sh
git push origin main
git push -u origin main # '-u' 업스트림 설정.
git push # 업스트림 설정시 간단하게 push
```
---

### pull이란?
Pull은 원격 저장소의 변경 내용을 가져와 로컬 저장소에 반영하는 작업이다.
협업 중 다른 사람이 작업한 내용을 최신 상태로 유지하기 위해 사용된다.
```sh
git pull origin main
git pull # 업스트림 설정시 간단하게 pull

```
---

### clone 이란?
Clone은 원격 저장소를 로컬 저장소로 그대로 복사하는 작업이다.
프로젝트의 파일뿐 아니라 커밋 이력과 구조까지 함께 가져오며, 협업 프로젝트에 처음 참여할 때 사용된다.
```sh
git clone https://github.com/username/repository.git #<URL>.git
```
