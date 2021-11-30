# 코드잇 유닉스 커맨드

- 터미널 : 인풋을 받고 아웃푹을 출력해주는 프로그램
- shell : 커맨드를 해석해 주는 프로그램
    - 커맨드(ex.date, cal)를 컴퓨터가 이해할수 있는 형태로 바꿔줌
    - bash(Bourne again shell)이 shell의 종류 중 하나.
- prompt(프롬프트) : 시스템이 다음 명령이나 메시지, 또는 다른 사용자의 행동을 받아들일 준비가 되었음을 사용자에게 알려주는 메시지 [네이버 국어사전]
- `~` : 사용자의 홈폴더를 듯함
- `date` : 현재 시간과 날짜 출력
- `cal` : 이번달 달력 출력
- `cal 10 2021` : 2021년 10월 달력 출력
- **argument(아규먼트):인자** - 어느 대상에 대해 커맨드를 실행할지를 정해줌.
    - `cal 10 2021` 에서 '10 2021'이 아규먼트
- **option(옵션)** : 커맨드의 실행되는 방식을 변경할 수 잇음.
    - `cal -j 10 2020` : 1월 1일부터 몇번째 날인지를 보여줌
        
        `cal -y 2020` : 2020년의 달력 전체 출력
        
        `cal -yj 2020`/ `cal -j 2020` : 위 두개를 동시에 (y가 없어도 월 값이 없어서 동일하게 출력됨)