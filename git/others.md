## 1. 수정한 내용 저장하고 병합하기

```bash
git add *
git commit -m "..."
git pull
```

## 2. 임시로 변경 내용 보관

```bash
git stash
git pull
git stash pop
```

## 3. 로컬 변경 내용 버리고 원격으로 덮어씌우기

```bash
git reset --hard
git pull
```
