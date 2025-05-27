# Git 디렉토리 이력 유지하여 분리하는 방법

- 특정 디렉토리만 남기고 해당 부분의 커밋 이력까지 포함하여 새 GitHub 저장소로 옮길 때 사용

### 1. `git-filter-repo` 설치

```bash
pip install git-filter-repo
```

### 2. `git-filter-repo` 경로 확인

***[Window]***

```bash
pip show git-filter-repo
```

- Location: **YOUR_PATH**\Lib\site-packages
- 경로 복사 필요

***[Mac/Linux]***

```bash
git filter-repo --help
```

- 바로 활용 가능

### 3. 기존 저장소 복제

```bash
git clone https://github.com/yourname/original-repo.git
cd original-repo
```

### 4. 디렉토리 필터링

***[Window]***

```bash
python YOUR_PATH\Scripts\git-filter-repo.exe --subdirectory-filter docs
```

***[Mac/Linux]***

```bash
git filter-repo --subdirectory-filter docs
```

### 5. 새 저장소에 푸시

```bash
git remote remove origin
git remote add origin https://github.com/yourname/new-repo.git
git push -u origin main
```

- GitHub에 새 저장소를 만들 때 `README.md`, `.gitignore` 없이 만들면 충돌 없이 바로 push 가능
- 이미 초기 커밋이 있는 경우 `git pull origin main --allow-unrelated-histories` 이후 push

