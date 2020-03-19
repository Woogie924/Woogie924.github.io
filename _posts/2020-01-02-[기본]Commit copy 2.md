---
title: "기본 commit"
category:
  - post
tag:
  - git
toc: true
---


#### 파일을 관리 대상 파일(Tracked)상태로 만들기 <br>
###### index영역에 파일 보내기<br>
```bash
$ git add <파일이름>
```
###### 파일을 커밋하기 -  (index 영역)->(commit 장소)<br>
```bash
$ git commit -m "first commit"
```
- - -
#### 커밋하기<br>
1. 명령어 입력<br>
```bash
$ git commit
```
<br>
2. 'i' 입력<br>
3. 커밋메시지 입력<br>
4. ESC 입력<br>
5. ':' 세미콜론 입력<br>
6. wq입력<br>

#### 커밋하기 - 인라인
```bash
$ git commit -m "커밋 메시지 입력"
```

- - -
#### 커밋 히스토리 조회하기
1. 전체 조회
```bash
$ git log
```

2. -p는 각 커밋의 diff결과, -2는 최근 두개의 결과
```bash
$ git log -p -2
```

3. 각 커밋 통계 정보 조회
```bash
$ git log --stat
```

4. 조회 범위 제한 옵션
```bash
$ git log --since==2.weeks
//2주까지의 내용
```

5. 코드 추가, 제거된 내용 중 특정 텍스트 포함하는 친구 검색
```bash
$ git log -S "특정 텍스트"
```

