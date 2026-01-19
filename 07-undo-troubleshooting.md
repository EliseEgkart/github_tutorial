# 되돌리기와 문제 해결

## 목표
- 실수했을 때 되돌리는 방법 정리
- 자주 발생하는 문제와 해결책 기록

## 핵심 개념
- `reset` vs `revert`
- `stash`로 임시 저장
- 복구 흐름

## 주요 명령어
- `git restore`
- `git reset`
- `git revert`
- `git stash`
- git commit --amend
- git merge --abort

## 예시
```sh
git restore --staged path/to/file
git reset --soft HEAD~1
git revert HEAD
git stash push -m "wip"
```

## 메모
- TODO: 팀에서 허용하는 복구 전략 추가
