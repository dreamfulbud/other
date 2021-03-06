# 코드잇 유닉스 커맨드
- CLI(Command-Line Interface) : 커맨들를 입력해서 컴퓨터를 사용하는 환경
- 터미널(terminal): 인풋을 받고 아웃푹을 출력해주는 프로그램

- shell : 커맨드를 해석해 주는 프로그램
    - 커맨드(ex.date, cal)를 컴퓨터가 이해할수 있는 형태로 바꿔줌
    - bash(Bourne again shell)이 shell의 종류 중 하나.
- prompt(프롬프트) : 시스템이 다음 명령이나 메시지, 또는 다른 사용자의 행동을 받아들일 준비가 되었음을 사용자에게 알려주는 메시지 [네이버 국어사전]

- 커맨드 
  - `~` : 사용자의 홈폴더를 듯함
  - `date` : 현재 시간과 날짜 출력
  - `cal` : 이번달 달력 출력
  - `cal 10 2021` : 2021년 10월 달력 출력
  - 
- 커맨드에는 아큐먼트와 옵션을 줄 수 있음
  - **argument(아규먼트):인자** - 어느 대상에 대해 커맨드를 실행할지를 정해줌.
    - `cal 10 2021` 에서 '10 2021'이 아규먼트
  - **option(옵션)** : 커맨드를 어떻게 실행할 것인지, 커맨드의 실행되는 방식을 변경할 수 잇음.
    - `cal -j 10 2020` : 1월 1일부터 몇번째 날인지를 보여줌
    - `cal -y 2020` : 2020년의 달력 전체 출력
    - `cal -yj 2020`/ `cal -j 2020` : 위 두개를 동시에 (y가 없어도 월 값이 없어서 동일하게 출력됨)

### man : 매뉴얼
- `man cal` : cal 커맨드를 아규먼트로 넘겨 cal의 매뉴얼을 볼 수 있음.
- 아래쪽 방향키/위쪽 방향키 : 한줄씩 이동
- `space`/ `f` : 페이지단위로 내려감 / `b` : 페이지단위로 올라감

### 터미널 사용 꿀팁
- **위쪽 방향키** : 이전 실행 커맨드를 볼 수 있음.
- `ctrl + A` : 줄 가장 앞 부분으로 커서 이동.
- `ctrl + E` : 줄 가장 뒷 부분으로 커서 이동.
- `option + 왼쪽방향키` : 단어단위로 커서 이동
- `ctrl + C` : 입력 취소
- `clear` : 커맨드창 깨끗하게 지우기
- `tab`: 자동완성

---

### 유닉스 폴더 구조와 파일 경로
- `/` : root 디렉토리
- `/Users` :User(macOS) / `/home` : home(Linux) 디렉토리 
- `~`, `/Users/dreamfulbud` 사용자의 홈 디렉토리
  - 사용자가 2명 이상이라면 디렉토리가 늘어남.
  - 각종 문서 / 바탕화면 파일 / 다운로드 파일
- `~/Desktop`, `/Users/dreamfulbud/Desktop` : 바탕화면 디렉토리

### 디렉토리와 파일 둘러보기 : pwd, cd, ls
- 보통 터미널을 열면 홈 디렉토리 `~` 에서 시작 
- Working Directory : 현재 위치해 있는 디렉토리
- `pwd` : 현재 위치 경로 (Print Working Directory)
- `cd` : 경로 변경 (Change Directory)
  - `cd /` : root 디렉토리로 이동
  - `cd ~`, `cd`: 홈 디렉토리로 이동
  - `cd -` : 이전 디렉토리로 이동
  - `cd ..` : 상위(부모) 디렉토리로 이동
- `ls` : 디렉토리의 내용을 리스트로 보여줌 (List)
  - `ls /Users` : 해당(Users) 디렉토리의 내용을 리스트로 보여줌

### 절대 경로와 상대경로
- 상대경로 : 현재 자신의 위치해 있는 디렉토리(Working Directory) 기준으로 경로를 나타냄.
- `.` : 현재 디렉토리를 표시
- `..` : 상위 디렉토리를 표시
- `../..`
- 경로를 아규먼트로 받는 모든 커맨드에 절대경로, 상대경로 둘다 사용 가능.

- 디렉토리에 공백이 있을때
  - `cd 'hello world'`
  - `cd "hello world"`
  - `cd hello\ world`
- 사실 파일이나 디렉토리 이름에는 애초에 공백을 안 사용하는게 더 바람직!!!
  - hello_world

### ls의 중요한 옵션들
- `ls -a` : all의 약자. 숨김파일까지 보여줌
- `ls -l` : long format의 약자. 추가정보를 보여줌
- `ls -al` : 숨김파일+추가정보

### root 디렉토리 안에는 어떤 것들이 있을까?
- `/bin` 
  - binaries의 약자. 컴퓨터가 실행할 수 있는 프로그램을 뜻함. 
  - 커맨드도 결국 어떤 프로그램. 커맨드를 입력하면 커맨드에 해당하는 프로그램이 실행되는 것. 그리고 그 프로그램의 일부는 `/bin` 디렉토리 안에 있음.
- `/sbin`: 관리자 전용 프로그램
- `/etc` : 컴퓨터 설정 파일. 관리자 권한 설정 파일
- `/home` 또는 `/Uers` : 사용자들의 홈 디렉토리. 사용자의 모든 파일을 저장해 놓은곳. 
- `usr` : 사용자에게 필요한 파일 저장. 
  - `/bin`: 컴퓨터가 시작하거나 자신을 수리하기 위해서 꼭 필요한 커맨드들이 있음
  - `/usr/bin`: 컴퓨터가 필요하기보다는 사용자가 필요한 커맨드들이 있음. 
  - `/usr/loacal`: 사용자가 직접 설치한 프로그램과 관련된 파일


### 디렉토리 파일 만들기
- `mkdir`: 폴더 만들기 ex)mkdir folder1 forder2
- `touch`: 파일 업데이트/생성 ex)touch file1.txt file2.txt

### CLI 텍스트 에디터 vim
- `vim`
- `vim path/to/file`과 같이 파일경로를 아규먼트로 주면 해당 파일을 열거나, 존재하지 않으면 새로 만들어 줌.
  
- |일반모드(esc)|입력모드(i)|비주얼모드(v)|명령모드(:)|
  |---|---|---|---|
  |커서이동|텍스트입력|텍스트 블록 지정|내용저장|
  |텍스트 붙여넣기| |텍스트 복사| vim 종료|
  |작업취소||||
- 텍스트 복사, 잘라내기, 붙여넣기
  1.  복사를 하고싶은 곳으로 커서 이동
  2.  줄단위로 복사하고 싶을땐 대문자V / 글자단위 복사하고 싶을땐 소문자v
  3.  복사: y
  4.  잘라내기: d
  5.  붙여넣기: p
  6.  비주얼모드 없이 yy /dd / p 사용도 가능
- 파일저장 :`:w` (명령모드)
- 파일 저장 및 종료 : `:wq`
- 저장없이 종료 `:q!`

### cat
- `cat file.txt`
- 파일내용 간단하게 확인
- concatenate(이어붙이다)
- `cat file.txt file2.txt` 
### less
- `less file.txt`
- 파일을 페이지단위로 보여줌

### head/tail
- head: 파일의 시작부분 확인
- tail: 파일의 끝부분 확인 
- `head -n 5 file.txt` 줄 개수 변경 가능

### 디렉토리 파일 옮기기, 이름 변경하기
- `mv`(move)
- `mv 경로1 경로2` 작업의 대상의 경로/이동할 목적지 또는 변경할 이름
- 주의할것! 똑같은 파일의 이름이 있을때 덮어쓰기됨!
  - `mv -i test1.txt test2.txt`: `-i` 는 overwirte 여부를 물음.

### 파일 복사 붙여넣기
- `cp`(copy) 
- `cp 경로1 경로2` 복사할 대상의 경로 및 파일 / 복사할 위치 혹은 파일명(없으면 생성)
- 주의할것! 똑같은 파일의 이름이 있을때 덮어쓰기됨!
  - `cp -i test.txt ../folder1`: `-i` 는 overwirte 여부를 물음.
  - `cp -r folder1 folder1_copy`: `-r` 폴더 복사시 옵션 필요! (재귀적 복사)

### 파일 삭제하기 
- `rm`(remove)
- `rm 경로1 경로2 ...` 삭제할 파일 또는 폴더 경로 
- `rm -r folder1`: 폴더삭제시엔 `-r` 옵션 필수
- `rm -ri folder1`: 파일 하나하나 씩 확인하면서 삭제
- 삭제시 휴지통 이동이 아니라 영구적 삭제!
- `-f`:삭제여부 물어보지 않고 삭제 `rm -rf folder1`

### sudo
- 관리자 권한을 가지고 command 실행.