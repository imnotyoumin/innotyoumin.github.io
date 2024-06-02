# innotyoumin.github.io

리눅스 명령어
-

Linux Top 명령어
=

## top 명령어란?   
▶ 리눅스에서 실행 중인 프로세스들의 실시간 정보를 보여줌 (CPU / 메모리의 사용량 및 프로세스 단위의 리소스 사용량)   

## top 의 실행 결과는 다음과 같다.   
<img width="583" alt="top 명령어" src="https://github.com/imnotyoumin/innotyoumin.github.io/assets/86357840/f951115a-622b-4c2e-afe2-d7139b755480">


__PID__   
=> 프로세스 ID (PID)   

__User - User Name__    
=> 프로세스를 시작한 사용자의 유효한 사용자 ID 이다. (사용자 ID와 매핑)   

__PR - Priority__   
=> 작업의 예약 우선 순위, **rt**가 표시되면 작업이 실시간 예약 우선 순위로 실행되어지고 있음을 의미 한다.   

__NI - Nice Value__   
=> 작업의 Nice 값으로 음수이면 우선 순위가 높고 양수이면 우선순위가 낮다.   

__VRIT - Swapped size (kb)__   
=> 작업에 사용된 총 가상 메모리 양, 프로세스가 사용하고 있는 가상 메모리의 전체 용량(SWAP + RES)이다.   

__RES - Resident size (kb)__   
=> 현재 프로세스가 사용하고 있는 물리 메모리 양, 실제 사용하고 있는 메모리 양을 확인하려면 RES값을 확인하면 된다.   

__SHR - Shared Mem size (kb)__   
=> 공유 메모리 크기, 다른 프로세스와 공유하고 있는 공유 메로리의 양 이다.   

__S - Process Status__
=> 프로세스 상태를 나타낸다.   

프로세스 문자표는 다음과 같다.   
| 형태 | 기능 |
| -- | ----------- |
|D|무중단 Sleep 상태(Uninterruptible Sleep), 디스크 혹은 네트워크 I/O를 대기|
|I|Idle|
|R|Running, 실행 중(CPU 자원을 소모)|
|S|Sleeping, 요청한 리소스를 즉시 사용 가능|
|T|작업 제어 신호(Job Control Signal)에 의해 중지된다.|
|t|Trace 중 디버거에 의해 중지된다.|
|Z|Zombie, 부모 프로세스가 죽은 자식 프로세스|   

__%CPU - CPU usage__   
=> CPU 사용비율의 추정치이다.   

__%MEM - Memory usage (RES)___   
=> 사용한 실제 메모리의 양이다.   

__TIME+ - CPU Time__   
=> CPU의 총 사용시간이다.   

__COMMAND - Command line or Program name__   
=> 프로세스를 실행한 커맨드이다.

## **리눅스 사용옵션**   
| 형태 | 기능 |
| - | - |
|-d| 갱신주기 조절|
|1|CPU 코어별 사용 현황|
|m|메모리 사용률 시각화 표현|
|shift + p|CPU 사용률이 높은 프로세스를 기준으로 나열|
|shift + m|메모리 사용률이 높은 프로세스를 기준으로 나열|
|shift + t|수행 시간이 긴 프로세스를 기준으로 나열|
|k|kill 할 프로세스의 PID를 입력할 수 있음|
|b|Batch 모드로 작동|
|u|모니터링할 user를 선택하여 해당 권한 프로세스 감시|
-----------------------------------------------

Linux ps 명령어
=
## ps란?   
Process Status의 줄임말로 ps 명령어는 현재 실행중인 프로세스 목록과 상태를 보여준다.   

## 주요 옵션   
| 형태 | 기능 |
| - | - |
|-A|모든 프로세스 출력|
|-e|커널 프로세스를 제외한 모든 프로세스를 출력|
|-f|츨력을 full 포멧으로 표기|
|-l|출력을 long 포멧으로 표기|    

## $ ps -ef : 모든 프로세스를 풀 포멧으로 출력    
결과는 다음과 같다.   
<img width="455" alt="ps" src="https://github.com/imnotyoumin/innotyoumin.github.io/assets/86357840/027a6740-8f3f-41ad-83e0-82b4721af238">    

**UID**   
=> 실행 유저   

**PID**   
=> 프로세스 ID   

**PPID**   
=> 부모 프로세스 PID   

**C**   
=> CPU 사용량   

**STIME**   
=> 프로세스가 시작된 시간 or 날짜   

**TTY**   
프로세스와 연결된 터미널   

**TIME**   
=> 총 CPU 사용 시간   

**CMD**   
=> 프로세스 실행 명령어

## BSD 계열 옵션   
| 형태 | 기능 |
| - | - |
|a|모든 사용자|
|u|프로세스의 사용자/소유자|
|x|데몬 프로세스(터미널 세션이 끊겨도 구동되는 프로세스)|
|f|프로세스 상속관계를 트리구조로 출력|
|ww|넓게(Wide)|   

$ ps aux : 실행중인 모든 프로세스 확인   
실행 결과는 다음과 같다.   

<img width="576" alt="ps aux" src="https://github.com/imnotyoumin/innotyoumin.github.io/assets/86357840/f50a280a-b002-424b-86ae-a5db24be80b5">   

**VSZ**   
=> K 단위 또는 페이지 단위의 가상 메모리 사용량   

**RSS**   
=> 실제 메모리 사용량   

**STAT**   
=> 현재 프로세스의 상태 코드   

**COMMAND**   
=> 프로세스의 실행 명령행   

--------------
ps와 top의 차이점
=
1.ps는 **ps한 시점에 proc에서 검색한 cpu 사용량**
2.top은 **proc에서 일정 주기로 합산해 cpu 사용율 출력**   

----------------
Linux jobs 명령어
=

## job이란?   
Jobs 명령어는 작업의 상태를 표시하는 명령어이다. 현재 쉘 세션에서 실행시킨 백 그라운드 작업의 목록이 출력되며,   
각 작업에는 번호가 붙어 있어 kill 명령어 뒤에 '% 번호' 등으로 사용할 수 있다.   

Jobs[옵션][작업번호]   

##jobs 사용법   
jobs로 출력되는 백그라운드 작업의 상태값
| 상태 | 기능 |
|-|-|
|Running|작업이 계속 진행중|
|Done|작업이 완료되어 0을 반환|
|Done(code)|작업이 완료되었으며 0이 아닌 코드를 반환|
|Stopped|작업 일시 중단|
|Stopped(SIGTSTP)|SIGTSTP 시그널이 작업을 일시 중단|
|Stopped(SIGSTOP)|SIGSTOP 시그널이 작업을 일시 중단|
|Stopped(SIGTTIN)|SIGTTIN 시그널이 작업을 일시 중단|
|Stopped(SIGTTOU)|SIGTTOU 시그널이 작접을 일시 중단|

## 주요 옵션

| 옵션 | 기능 |
|-|-|
|-l|프로세스 그룹 ID를 state필드 앞에 출력|
|-n|프로세스 그룹 중에 대표 프로세스 ID를 출력|
|-p|각 프로세스 ID에 대해 한 행씩 출력|
|command|지정한 명령어를 실행|

---------------------------
Linux kill 명령어
=

## kill 이란?   
kill 명령어는 프로세스에 시그널을 보내는 명령어이다.   

## kill 사용법   
kill 시그널 리스트 확인   
$ kill -l   
<img width="596" alt="kill 리스트" src="https://github.com/imnotyoumin/innotyoumin.github.io/assets/86357840/6507cd8a-0020-4f6b-a687-b20ef87f8582">   

주요 시그널   
|시그널|영어|기능|
|-|-|-|
|1) SIGHUP|Hang Up|세션이 종료될 때 시스템이 내리는 시그널|
|2) SIGINT|Interrupt|CTRL + C, 종료 요청 시그널|
|9) SIGkill|kill|강제 종료 시그널|
|11) SIGSEGV|Segment Violation|메모리 침범이 일어날 때 시스템이 보내는 시그널|
|15) SIGTERM|Terminate|기본값, 종료 요청 시그널|   
|20) SIGTSTP|Temporary Stop|CTRL+Z 일시 중지 요청 시그널|   

## 프로세스에 시그널 보내는 법   
$ kill [option] PID   
ex) 2311(PID) 프로세스 종료   
=> $ kill -9 2311 or $ kill -SIGKILL 2311


