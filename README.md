# innotyoumin.github.io

리눅스 명령어
-

__Top 명령어__

top 명령어란?   
▶ 리눅스에서 실행 중인 프로세스들의 실시간 정보를 보여줌 (CPU / 메모리의 사용량 및 프로세스 단위의 리소스 사용량)   

 top -b -n 1 예시
<img width="612" alt="top 명령어" src="https://github.com/imnotyoumin/innotyoumin.github.io/assets/86357840/b754e586-49d9-47fd-8219-1f5b37e85600">   

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
| 이름 | 기능 |
| -- | ----------- |
|D|무중단 Sleep 상태(Uninterruptible Sleep)|
|I|Idle|
|R||Running|
|S|Sleeping|
|T||작업 제어 신호(Job Control Signal)에 의해 중지된다.|
|t|Trace 중 디버거에 의해 중지된다.|
|Z|Zombie|
