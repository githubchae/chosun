# helloworld_20213037

1.	리눅스 명령어 : top, ps, jobs, kill 명령어 조사하기

<top>
  
•	시스템의 상태를 전반적으로 가장 빠르게 파악 가능(CPU, Memory, Process)
  
•	옵션 없이 입력하면 interval 간격(기본 3초)으로 화면을 갱신하며 정보를 보여줌
  
•	top 실행 전 옵션
  
  o	순간의 정보를 확인하려면 -b 옵션 추가(batch 모드)
  
  o	-n : top 실행 주기 설정(반복 횟수)
  
•	top 실행 후 명령어
  
  o	shift + p : CPU 사용률 내림차순
  
  o	shit + m : 메모리 사용률 내림차순
  
  o	shift + t : 프로세스가 돌아가고 있는 시간 순
  
  o	k : kill. k 입력 후 PID 번호 작성. signal은 9
  
  o	f : sort field 선택 화면 -> q 누르면 RES순으로 정렬
  
  o	a : 메모리 사용량에 따라 정렬
  
  o	b : Batch 모드로 작동
  
  o	1 : CPU Core별로 사용량 보여줌
  
•	시스템의 상태를 전반적으로 가장 빠르게 파악 가능(CPU, Memory, Process)
  
•	옵션 없이 입력하면 interval 간격(기본 3초)으로 화면을 갱신하며 정보를 보여줌
  
•	top 실행 전 옵션
  
  o	순간의 정보를 확인하려면 -b 옵션 추가(batch 모드)

  o	-n : top 실행 주기 설정(반복 횟수)

•	top 실행 후 명령어
  
  o	shift + p : CPU 사용률 내림차순
  
  o	shit + m : 메모리 사용률 내림차순
  
  o	shift + t : 프로세스가 돌아가고 있는 시간 순
  
  o	k : kill. k 입력 후 PID 번호 작성. signal은 9
  
  o	f : sort field 선택 화면 -> q 누르면 RES순으로 정렬
  
  o	a : 메모리 사용량에 따라 정렬
  
  o	b : Batch 모드로 작동
  
  o	1 : CPU Core별로 사용량 보여줌

<ps>
  
•	현재 실행중인 프로세스의 목록을 보는 명령어
  
•	옵션
  
  o	e: 실행중인 모든 프로세스의 정보를 출력한다.
  
  o	f: 프로세스에 대한 자세한 정보를 출력한다.(PPID 확인 가능)
  
  o	u [사용자이름] : 특정 사용자에 대한 모든 프로세스의 정보를 출력
  
  o	p pid: pid로 지정한 프로세스의 정보를 출력
  
  o	u: 프로세스 소유자의 이름, cpu 사용량, 메모리 사용량 등 상세정보를 출력
  
  o	a: 터미널에서 실행한 프로세스의 정보를 출력
  
  o	x: 실행 중인 모든 프로세스의 정보를 출력
  
•	ps와 top의 차이점
  
  o	ps는 ps한 시점에 proc에서 검색한 cpu 사용량
  
  o	top은 proc에서 일정 주기로 합산해 cpu 사용율 출력

<jobs>
  
•	작업의 상태를 표시하는 명령어.
  
•	현재 쉘 세션에서 실행시킨 백그라운드 작업의 목록이 출력되며, 각 작업에는 번호가 붙어있어 kill 명령어 뒤에 ‘%번호’ 등으로 사용할 수 있다.
  
  o	jobs [옵션][작업번호]
  
•	상태
  
  running
  
  done
  
  done(code)
  
  stopped
  
  stopped(sigtstp)
  
  stopped(sigstop)
  
  stopped(sigttou)
  
 
•	옵션
  
 -l 
  
 -n
  
 -p
  
 command

<kill>
  
•	응답이 없는 프로세스나 불필요한 프로세스를 강제로 종료하려면 해당 프로세스의 PID를 알아야 한다. Ps -ef나 ps aux명령으로 프로세스의 정보를 확인하면 PID와 PPID를 볼 수 있다. 프로세스를 종료하는 데는 kill과 pkill 명령을 사용한다. 이 명령들은 프로세스에 시그널을 보내어 프로세스를 종료한다.
  
•	kill 명령은 인자로 지정한 프로세스에 시그널을 전달한다.
  
  

  
  
  
 

2.	vim 에디터에서 매크로 사용방법에 대하여 조사하기 (q, @)
  
vi의 꽃이라고도 할 수 있는 macro(매크로)
  
매크로는 특정한 움직임 또는 입력을 키에 저장함으로써 단순하면서 반복되는 동작을 쉽고 빠르게 해주는 것을 말한다.

vi에서 매트로는 명령어 모드에서
  
q + 알파벳을 눌러 특정 알파벳에 매크로를 저장할 수 있다.

순서는
1. q + a       a키에 recording 시작
2. 반복을 위한 내가 원하는 동작
3. q             recoding 종료
4. @a          1회 실행
or @@         방금 실행한 매크로 실행
or 10@a       매크로 10회 실행

숫자 증가는 어떻게 하는가?
1. 1 숫자 입력
2. 매크로 시작
3. 1 숫자를 복사해서 다음줄에 붙여넣기
4. 두 번째 줄 1에 커서를 올리고 Ctrl+a(숫자 증가)
5. 매크로 종료

숫자 증가 매크로의 핵심 키는
ctrl + a (숫자 증가)
ctrl + x (숫자 감소)

