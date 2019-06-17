# Branch

### 브랜치 만들기

**$ git branch *branchname***

```ubuntu
$ git branch hello
```

```ubuntu
$ git branch
  hello
* master
```

### 브랜치 전환하기

**$ git checkout *branchname***

```ubuntu
$ git checkout hello
Switched to branch 'hello'
```

##### 브랜치 작성과 체크아웃 한꺼번에 실행

```ubuntu
$ git checkout -b hello
```

### 브랜치 병합하기

**$ git merge *commitbranch***

'HEAD'를 가리키고 있는 브랜치에 *commitbranch* 병합 

```ubuntu
$ git checkout master
Switched to branch 'master'
```

```ubuntu
$ git merge hello
```

### 브랜치 삭제하기

**$ git branch -d *branchname***

```ubuntu
$ git branch -d hello
```
