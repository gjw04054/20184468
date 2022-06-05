># 리눅스 명령어와 vim 매크로 _ 20184468
<br/>

>>## __1. 리눅스 명령어__
  * TOP
  * PS
  * JOBS
  * KILL

<br/>

### __1-1. Top__
    top 명령어는 현재 os의 상태를 나타내주는 CLI 어플리케이션(Command-line Interface)입니다. 
    메모리 사용량, CPU 사용량 등을 나타내주며 top를 실행하는 동안에는 주기적인 업데이트로 
    실시간에 근접한 내용을 보여줍니다.   
   
   ![TOP명령어](https://user-images.githubusercontent.com/45027599/172046858-d601dc5a-86d6-4174-ab4d-09f4b110c56c.png)


----
![image](https://user-images.githubusercontent.com/45027599/172047167-9b4567ad-35ce-4e20-9437-a04c4a011f50.png)


* **서버 정보 (첫번째 줄)**

    서버 정보를 담고 있는 줄로, TOP에서 상단에 위치하고 있습니다. 
    전체 프로세스가 OS에 대해서 리소스를 어느정도 차지하고 있는지 알려줍니다.
    
   + top - 현재 서버의 시간
   + up - 가동 중
   + 7 days, 1:15 - 7일, 1시간 15분째
   + 2 users - 2명의 사용자가 접속
   + load average - 부화율 
 
 * **프로세스 정보 (두번째 줄)**

    CPU Load의 이동 평균을 표시하고, 로드 애버리지 영역이라고 부릅니다. 
    
   + 129 total - 총 129개의 프로세스 가동 중
   + 1 running - 1개의 프로세스가 실행 중
   + 75 sleeping - 102개의 프로세스가 대기 중
   + 0 stopped - 0개의 프로세스가 멈춤
   + 0 zombie - 0개의 프로세스 좀비 상태

 * **CPU 사용량 (세번째 줄)**
   
    CPU가 어떻게 사용되고 있는지 사용률을 보여주는 영역입니다. 총 합은 100퍼센트이며 각 요소는 아래와 같습니다.
   
   + us : 프로세스의 유저 영역에서의 CPU 사용률
   + sy : 프로세스의 커널 영역에서의 CPU 사용률
   + ni : 프로세스의 우선순위(priority) 설정에 사용하는 CPU 사용률
   + id : 사용하고 있지 않는 비율
   + wa : IO가 완료될때까지 기다리고 있는 CPU 비율
   + hi : 하드웨어 인터럽트에 사용되는 CPU 사용률
   + si : 소프트웨어 인터럽트에 사용되는 CPU 사용률
   + st : CPU를 VM에서 사용하여 대기하는 CPU 비율
 
  * **메모리 정보 (네번째와 다섯 번째 줄)**
  
    Mem이라 표시된 부분은 RAM의 메모리 영역입니다. 그리고 Swap 영역은 디스크를 메모리 처럼 이용합니다. 
    일반적으로 Mem의 사용량이 거의 가득 찼을 때 Swap 메모리 영역을 사용합니다. 
    디스크이기 때문에RAM 메모리보다는 속도가 많이 느립니다.
    
    + total : 총 메모리 양
    + free : 사용가능한 메모리 양
    + used : 사용중인 메모리 양

  * **프로세스 상태 (그 이하 줄)**

    |요소|내용|
    |:---:|:---:|
    |PID|프로세스 ID|
    |USER|프로세스를 실행시킨 사용자 ID|
    |PR|프로세스의 우선순위|
    |NI|PR에 영향을 주는 nice라는 값 |
    |VIRT|가상 메모리의 사용량(SWAP+RES)|
    |RES|현재 페이지가 상주하고 있는 크기|
    |SHR|분할된 페이지, 프로세스에 의해 사용된 메모리를 나눈 메모리의 총합|
    |S|프로세스의 상태 -S(sleeping), R(running), W(swapped out process), Z(Zombies)|
    |%CPU|프로세스가 사용하는 CPU의 사용률|
    |%MEM|프로세스가 사용하는 메모리의 사용률|
    |COMMAND|실행된 명령어|

* **단축키 명령어**

    |명령어|설명|
    |:---:|:---:|
    |space|정보를 업데이트|
    |shift + p|CPU 사용률이 높은 프로세스 순서대로 표시|
    |shift + m|메모리 사용률이 높은 프로세스 순서대로 표시|
    |shift + t|프로세스가 돌아가고 있는 시간 순서대로 표시|
    |k|프로세스를 종료시킨다|
    |a|메모리 사용량에 따라 정렬|
    |b|Batch 모드|
    |c|명령행, 프로그램 이름 토글|
    |h|도움말|
    |n or #|출력할 프로세스의 수를 지정|
    |s|출력할 정보의 업데이트의 시간을 지정|
    |q|종료|

<br/>
<br/>

  ### __1-2. PS__
    ps는 process status의 줄임말이며, 현재 실행중인 프로세스 목록과 상태를 출력하여 보여주는 기능을 합니다.
    윈도우의 작업 관리자와 비슷합니다.
 
 <br/>
 
  * **자주 사용되는 ps 명령어 옵션**
    
    |명령어|설명|
    |:---:|:---:|
    |ps -ef|모든 프로세스를 풀 포맷으로 출력|
    |ps -ef|grep'프로세스명'|'프로세스명'의 프로세스 구동 확인|
    |ps aux|실행중인 모든 프로세스 확인|
    |ps auxf|실행 중인 프로세스를 트리구조로 출력|
    |ps auxfww|실행 중인 프로세스를 트리구조 + 모든 실행 중인 옵션 확인 가능|

    + $ps aux 결과 모습
![image](https://user-images.githubusercontent.com/45027599/172049211-221bd67e-1b2f-4c13-b022-39b3614e20bd.png)


      + USER : 프로세스의 소유자의 이름
      + PID : 프로세스 식별자, 참고로 PPID는 부모프로세스 식별자
      + %CPU : CPU 점유율 
      + %MEM : Memory 점유율 
      + VSZ : Virtual memory size (가상메모리 사용량, KB 혹은 페이지 단위)
      + RSS : Risident Set Size의 약어, 실제 메모리 사용량
      + STAT : Status code (BSD계열)
      + START : 시작 시간
      + TIME : 총 수행시간(=총 CPU사용시간)
      + COMMAND : 프로세스 수행 명령어


    + $ps -ef 결과 모습
![image](https://user-images.githubusercontent.com/45027599/172049248-cddb7b6f-dc56-4f23-af52-b3675d0c8d20.png)

    + $ps aux 결과 모습



 




     
    
    
    
