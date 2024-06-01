# innotyoumin.github.io

리눅스 명령어
-

Top 명령어
==

top 명령어란?   
▶ 리눅스에서 실행 중인 프로세스들의 실시간 정보를 보여줌 (CPU / 메모리의 사용량 및 프로세스 단위의 리소스 사용량)   

 top 의 실행 결과는 다음과 같다.   
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
|D|무중단 Sleep 상태(Uninterruptible Sleep)|
|I|Idle|
|R|Running|
|S|Sleeping|
|T|작업 제어 신호(Job Control Signal)에 의해 중지된다.|
|t|Trace 중 디버거에 의해 중지된다.|
|Z|Zombie|   

__%CPU - CPU usage__   
=> CPU 사용비율의 추정치이다.   

__%MEM - Memory usage (RES)___   
=> 사용한 실제 메모리의 양이다.   

__TIME+ - CPU Time__   
=> CPU의 총 사용시간이다.   

__COMMAND - Command line or Program name__   
=> 프로세스를 실행한 커맨드이다.

**리눅스 사용옵션**   
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
