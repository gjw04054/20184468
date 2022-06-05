># 리눅스 명령어와 vim 매크로 _ 20184468


>>## __1. 리눅스 명령어__
  * TOP
  * PS
  * JOBS
  * KILL

### __1-1. Top__
    top 명령어는 현재 os의 상태를 나타내주는 CLI 어플리케이션(Command-line Interface)입니다. 
    메모리 사용량, CPU 사용량 등을 나타내주며 top를 실행하는 동안에는 주기적인 업데이트로 
    실시간에 근접한 내용을 보여줍니다.   
   
   ![TOP명령어](https://user-images.githubusercontent.com/45027599/172046858-d601dc5a-86d6-4174-ab4d-09f4b110c56c.png)


----
* 서버 정보를 담고 있는 줄 (첫번째 줄)
![image](https://user-images.githubusercontent.com/45027599/172047167-9b4567ad-35ce-4e20-9437-a04c4a011f50.png)

    서버 정보를 담고 있는 줄로, TOP에서 상단에 위치하고 있습니다. 
    전체 프로세스가 OS에 대해서 리소스를 어느정도 차지하고 있는지 알려줍니다.
    
   + top - 현재 서버의 시간
   + up - 가동 중
   + 7 days, 1:15 - 7일, 1시간 15분째
   + 2 users - 2명의 사용자가 접속
   + load average - 부화율 
 
 * 프로세스 정보를 담고 있는 줄 (두번째 줄)

    CPU Load의 이동 평균을 표시하고, 로드 애버리지 영역이라고 부릅니다. 

     
    
    
    
