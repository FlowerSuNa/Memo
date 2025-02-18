## AWS에서 Github 레파지토리 Pull 할 때 오류 발생

- 21년 8월 13일부터 비번으로 로그인하는 방식을 지원하지 않음
- 따라서 SSH 설정 필요

### AWS 서버에서 SSH 키 생성

- SSH 키 생성

```bash
ssh-keygen -t rsa -b 4096 -C "your_email@example.com"
```

- SSH 키 확인 & 복사

```bash
cat ~/.ssh/id_rsa.pub
```

### Github에 SSH 키 등록

1. [GitHub SSH Keys 설정](https://github.com/settings/keys) 이동
2. [New SSH Key] 클릭 & Title 입력
3. 복사한 SSH 키 붙여넣기 & [Add SSH Key] 클릭

### AWS에서 Git 저장소 주소 변경

- 기존 저장소 주소 제거

```bash
git remote remove origin
```

- 저장소 추가

```bash
git remote add origin git@github.com:{github-username}/{repository-name}.git
```

- 저장소 확인

```bash
git remote -v
```

- Git pull

```bash
git pull origin master
```
