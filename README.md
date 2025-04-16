### Git 설정

#### Git 전역으로 사용자 이름과 이메일 주소를 설정

- GitHub 계정과는 별개임

```bash
git config --global user.name "(본인 이름)"
git config --global user.email "(본인 이메일)"

# 아래의 명령들로 확인
git config --global user.name
git config --global user.email
```

<br>

#### 기본 브랜치명 변경

```bash
git config --global init.defaultBranch main
git branch -M main
```

### .gitignore 작성

```bash
# 이렇게 #를 사용해서 주석

# 모든 file.c
file.c

# 최상위 폴더의 file.c
/file.c

# 모든 .c 확장자 파일
*.c

# .c 확장자지만 무시하지 않을 파일
!not_ignore_this.c

# logs란 이름의 파일 또는 폴더와 그 내용들
logs

# logs란 이름의 폴더와 그 내용들
logs/

# logs 폴더 바로 안의 debug.log와 .c 파일들
logs/debug.log
logs/*.c

# logs 폴더 바로 안, 또는 그 안의 다른 폴더(들) 안의 debug.log
logs/**/debug.log
```

### Vim 입력 모드

![Vim 모드 작업](/images/vim.png)

### Git 기본 명령어

```bash
git status
git commit -m "FIRST COMMIT"
git log
git diff

# 🛑 새로 추가된(untracked) 파일이 없을 때 한정
git commit -am "(메시지)"
```

<br>

---

### 깃 과거로 되돌리는 2가지 방법 Reset Vs Revert

- `reset` : 원하는 시점으로 돌아간 뒤 이후 내역(히스토리)들을 지웁니다.
- `revert` : 되돌리기 원하는 시점의 커밋을 거꾸로 실행합니다.

| revert  
추가한 것이 있으면 삭제하고 변경한 것이 있으면 변경전으로 되돌려서 새로운 커밋을 만듦
즉, 히스토리를 남기게 됨

#### reset

```bash
git reset --hard (돌아갈 커밋 해시)

# 💡 뒤에 커밋 해시가 없으면 마지막 커밋을 가리킴
git reset --hard
```

#### revert

```bash
git revert (되돌릴 커밋 해시)

# 💡 커밋해버리지 않고 revert하기
git revert --no-commit (되돌릴  커밋 해시)
```
