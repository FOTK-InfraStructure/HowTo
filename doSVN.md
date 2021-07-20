### 기본 버전 관리 활용법

1. 비어있는 디렉토리를 생성한 후 `TortoiseSVN → Create Repository here...` 순서로 클릭한다.

   ![2](https://user-images.githubusercontent.com/63279334/126307871-0b446c6a-cc5a-4d2f-b88a-a7c2a01758c6.png)


2. 아래와 같은 폴더 구조가 자동으로 생성된다.

   ![3](https://user-images.githubusercontent.com/63279334/126307914-7a6ed08c-db28-40ef-970d-12f8b3ee97c4.png)

   create folder structure를 누르면 기본 폴더 구조가 생성된다.

   이러면 repository가 생성된 것이다.

3. 하지만 아직 아무런 프로젝트가 없으므로 프로젝트를 생성해야한다.

  ![5](https://user-images.githubusercontent.com/63279334/126307927-3fd57ba4-d0fa-4df1-b31d-037944717118.png)

   testRepo를 생성한 폴더에서 새롭게 userA라는 폴더를 생성한 후 `TortoiseSVN -> import ...` 순서로 클릭하면 프로젝트 등록 화면이 나온다.

   원격 저장소가 있는 경우 URL에 해당 원격 저장소를 등록하면 되지만 테스트에서는 원격 저장소가 없으므로 로컬에 생성한 testRepo를 활용한다.

   URL 경로에 testRepo의 경로를 넣고 `OK`를 클릭한다.

4. 마찬가지로 비교가 될 userB라는 폴더도 생성한 후 testRepo를 등록한다.
5. userA 와 userB는 둘 다 같은 testRepo를 공유하고 있다.
6. 그 후 두 유저에서 모두 `SVN checkout` 을 수행한다.

   ![7](https://user-images.githubusercontent.com/63279334/126307997-9d104707-a39e-4ec0-a45b-bbc8e3eff7ed.png)

7. 그 후 checkout 된 testRepo에서 작업을 수행한다.

   ![8](https://user-images.githubusercontent.com/63279334/126308011-a114a54e-b4c6-4e4c-8845-ab19b3583f33.png)


8. userA가 새로운 작업을 수행하였다.

   ![9](https://user-images.githubusercontent.com/63279334/126308018-d98ab20a-6be9-4b3d-944e-b6b7e9e14c64.png)


9. 그리고 수행한 작업을 repository로 commit한다.

  ![10](https://user-images.githubusercontent.com/63279334/126308134-0b81b1a5-e2a1-4559-8127-64473ab8de01.png)

   ![11](https://user-images.githubusercontent.com/63279334/126308146-6918283a-75d5-4dbc-8e57-09da36fcc7f6.png)


10. 이제 userB에서 userA가 한 작업을 새롭게 받을 수 있다.

    이때 주의 할 점은 반드시 새롭게 작업을 받을 때 `SVN update`를 해주어야 한다.

    ![12](https://user-images.githubusercontent.com/63279334/126308174-5d0fc4ab-605d-42f1-a60c-ab3f3668ccba.png)


### 브랜치를 나눠서 작업하기

1. SVN에서 새로운 기능 개발을 위해서 브랜치 생성을 위해선 특정한 디렉토리 구조를 따라야한다.

   ![2](https://user-images.githubusercontent.com/63279334/126308385-72cd61ab-f282-4b08-aa74-516a224aba3c.png)


   userA가 새로운 기능을 위해 새로운 브랜치를 만들기 위해선 `repository 오른쪽 클릭 -> tortoiseSVN -> Branch/tag`를 클릭한다.

2. SVN은 프로젝트를 위한 특정한 디렉토리 구조를 따라야한다. 그래서 메인 작업파일들은 trunk에 저장하고, 새로운 기능을 위한 브랜치들은 branches라는 디렉토리에 저장한다.

   이를 위해 trunk, branches 디렉토리를 생성한다.

   그리고 branches 디렉토리 안에 새로운 branch를 생성한다.

![7](https://user-images.githubusercontent.com/63279334/126308841-3ecdbb02-fd93-437e-89e4-b2a7c4bb50a2.png)


   이때 특정한 버전에서 브랜치를 나누고 싶다면 `specific revision in repository` 를 클릭하고,

   trunk에서 새롭게 브랜치를 나눈다면 `HEAD revisition in the repository`를 선택한다.

3. 새로운 브랜치를 생성한 후 해당 브랜치로 이동하기 위해선 `switch` 를 클릭한다.

![8](https://user-images.githubusercontent.com/63279334/126308849-50af40c3-9ce4-461d-a381-6cd33679a25d.png)


4. 새롭게 생성한 브랜치로 switch한다.

  ![9](https://user-images.githubusercontent.com/63279334/126308871-100d0a2e-4c6e-4c54-871c-2184c7378745.png)


5. 이후 `SVN checkout` 을 클릭하면 생성한 브랜치로 새롭게 디렉토리를 생성하게 된다.


  ![10](https://user-images.githubusercontent.com/63279334/126308878-8d6fd364-115d-4c27-b831-8c14e20cef45.png)
   ![11](https://user-images.githubusercontent.com/63279334/126308886-b7756337-4cbe-451c-8204-a1a99edce057.png)


6. 새로운 브랜치에서 파일을 변경한다.


   ![12](https://user-images.githubusercontent.com/63279334/126308897-6db26d7e-ea16-4932-9732-49cce290828d.png)


7. `tortoiseSVN -> diff` 를 통해서 원본 파일과의 차이를 확인할 수 있다.


   ![13](https://user-images.githubusercontent.com/63279334/126308909-4b6672c4-3137-4ce0-a54b-94276c437853.png)


8. 새로운 작업을 커밋한다.


![14](https://user-images.githubusercontent.com/63279334/126309186-52f6699c-b514-4eb1-9290-2291700f9c85.png)

![15](https://user-images.githubusercontent.com/63279334/126309197-f68b697b-4f94-4652-835b-a7b82eb16f86.png)




9. 이제 메인 trunk에 새로운 작업 내용을 `merge` 한다.

![2 (1)](https://user-images.githubusercontent.com/63279334/126309390-5947f99b-c0cd-4cf0-888e-ab9e4dd7f793.png)



10. `URL to merge from` 엔 새롭게 생성한 브랜치가 위치한다.

    ![3](https://user-images.githubusercontent.com/63279334/126309266-74feb9b8-8bbd-4dcd-954e-1a787ee064c6.png)


    show log를 클릭하면 변화된 기록을 확인 할 수 있고 변화된 특정 내용만 골라서 머지 할 수 있다.

11. 머지하기 이전에 `test` 를 통해 머지가 안전하게 정상적으로 이루어질 수 있는지 확인할 수 있다.

    ![5](https://user-images.githubusercontent.com/63279334/126309285-16fb646e-c1ee-4176-a992-e9459b29a1b0.png)


12. 머지된 내용을 repository로 commit한다.
13. 머지된 기록들을 `tortoiseSVN -> revision graph` 에서 확인할 수 있다.

![2 (2)](https://user-images.githubusercontent.com/63279334/126309318-47891399-22aa-47b6-abba-963e5e4df90f.png)


### 충돌 해결법

1. userA와 userB가 같은 파일을 다르게 작업하였다.

   userA

   ![2](https://user-images.githubusercontent.com/63279334/126309647-e602d5ee-c6e6-44cc-81db-0f400ee1a159.png)

   userB

   ![3](https://user-images.githubusercontent.com/63279334/126309657-9de9e457-b4bc-4fc9-917c-f294fb1fe4e9.png)


2. user A가 먼저 commit을 하고 user B가 이후에 commit을 한다.
3. 이 경우 user B에게 `confit` 가 발생한다.

   ![5](https://user-images.githubusercontent.com/63279334/126309670-49bd29a3-7bfd-4bc5-bfd2-25174fb58ba3.png)

   confict 부분을 더블클릭한다.

4. 어떤 부분에서 충돌이 났는지를 보여주는 화면이 나온다.

   ![6](https://user-images.githubusercontent.com/63279334/126309671-8453bfcc-99bf-48e7-b7af-e89e781ccd1e.png)

5. 이 화면에서 내 파일을 사용해서 상대방의 파일을 덮을지, 상대방의 파일을 사용해서 내 파일을 덮을지 결정할 수 있다.

   < 상대방의 파일로 내 파일을 덮는 경우 >

   ![7](https://user-images.githubusercontent.com/63279334/126309681-e5c31426-431e-4635-89f3-3217d40ba059.png)


   < 내 파일로 상대방의 파일을 덮는 경우 >

  ![8](https://user-images.githubusercontent.com/63279334/126309857-d2647d22-14aa-4aa7-a4ac-e6722309fb88.png)


6. 내 파일로 상대방의 파일을 덮었다.

   ![9](https://user-images.githubusercontent.com/63279334/126309868-2fa2aaf7-6170-4b4d-9502-1df0d9f42068.png)

   맨 아래에 합쳐진 파일에서 내 파일의 내용으로 덮인 것을 확인 할 수 있다.

   그리고 `Mark as resolved` 를 클릭하여 내용을 확인하고 `save` 한다.

7. 이제 repository에는 내가 수정한 내용으로 파일이 올라가 있는 상태이다.
8. user A를 update하면 수정한 파일의 내용으로 변한것을 확인할 수 있다.

  ![11](https://user-images.githubusercontent.com/63279334/126309876-29a37ea1-b7f4-40f0-8eb7-d70099944e42.png)


### 저장소 이동하기

1. `testRepo`라는 저장소가 존재하다가 모종의 이유로 사라졌다고 하자.

   ![2](https://user-images.githubusercontent.com/63279334/126309889-7cf707ea-3800-42cf-9f6a-0f32cba414df.png)

   ![3](https://user-images.githubusercontent.com/63279334/126309895-b08ebe5c-9140-48bf-a4dc-af1bb0b97c0b.png)

   이런 사실을 모르고 userA가 자신의 변경 사항을 저장소에 반영하려고 하면 저장소에 연결할 수 없다는 문제가 발생한다.

   ![4](https://user-images.githubusercontent.com/63279334/126309903-fddf51b7-bdd3-455c-82ab-99c448d696e1.png)


2. 우선 새로운 저장소를 생성한다.

   ![5](https://user-images.githubusercontent.com/63279334/126310195-bd2fee29-8cc4-4f98-9ff9-ebf94196b20a.png)

   `anotherRepo` 라는 저장소를 새롭게 만든다.

3. svn엔 저장소를 이동하는 기능인 `relocate` 가 존재한다.

  ![11](https://user-images.githubusercontent.com/63279334/126310211-fea9e602-f485-4bcf-98d7-ae3944223f2e.png)


4. 하지만 기존의 저장소와 새로운 저장소의 uuid가 다르다는 이유로 relocate를 활용할 수가 없다.

   ![4](https://user-images.githubusercontent.com/63279334/126310223-25d754fe-b21d-41a6-bb89-7486fde4a854.png)


5. 그래서 `anotherRepo -> db -> uuid` 파일에서 기존 프로젝트의 uuid와 같도록 `anotherRepo` 의 uuid를 수정한다.

   ![5 (1)](https://user-images.githubusercontent.com/63279334/126310228-7305aec3-3cb7-4d55-9cc0-2e80a33e4869.png)


6. 다시 `relocate` 를 실행하면 정상적으로 저장소가 이동됐다는 메시지가 나온다.

   ![6](https://user-images.githubusercontent.com/63279334/126310238-e4817027-130e-4726-8da3-3b621fb51edb.png)


7. 이후 파일을 변경하고 commit을 한다.
8. 하지만 커밋이 정상적으로 되지 않는다....

   ![8](https://user-images.githubusercontent.com/63279334/126310250-8da0abee-b6b2-4a4b-8501-77d23cd19236.png)


9. 따라서 수동으로 다른 방법을 사용해야한다.

   기존의 저장소에서 `export` 를 통해 기존의 내용들을 추출한다.

  ![6 (1)](https://user-images.githubusercontent.com/63279334/126310258-6064e6a5-40d1-4e85-a478-02e2d29981c5.png)


   아래와 같은 디렉토리들이 추출된다.

   ![7](https://user-images.githubusercontent.com/63279334/126310263-81be9588-fe68-4802-beed-86d256066820.png)

10. 추출된 디렉토리들을 새롭게 생성한 `anotherRepo` 에 넣어주면 저장소를 이동시킬 수 있다.

   ![8 (1)](https://user-images.githubusercontent.com/63279334/126310270-75b4098b-ec69-4b81-8fbb-3c80467aa5bf.png)


    ![9](https://user-images.githubusercontent.com/63279334/126310277-ab09754a-fdb3-4bb0-8897-4fb7f50cfecf.png)

11. `anotherRepo` 를 확인해보면 기존의 저장소의 내용을 모두 가져온 것을 볼 수 있다.

   ![10](https://user-images.githubusercontent.com/63279334/126310286-3c63a505-c0d5-4d3d-95bf-1241abaa0bd8.png)


    ![11 (1)](https://user-images.githubusercontent.com/63279334/126310292-c5dae503-9a6d-49d3-8970-763dcbced843.png)


12. 하지만 이 경우에도 기존에 작업하던 디렉토리에서 commit은 불가능하다.
13. 따라서 새롭게 생성한 저장소로 다시 checkout을 통해 작업 디렉토리를 생성한 후 작업을 이어나가야 한다.

   ![15](https://user-images.githubusercontent.com/63279334/126310297-243f3598-87b0-41f4-869b-8b74f59e3865.png)


### 외부저장소에서 사용하기

1. azure의 무료계정을 활용해서 remote svn 서버를 생성할 것이다.

   ![3](https://user-images.githubusercontent.com/63279334/126310308-d33919c6-57a7-4c16-a450-7518d525124b.png)
   
   ![4 (1)](https://user-images.githubusercontent.com/63279334/126310317-1a056c62-ce69-4c16-897a-164213ec154b.png)


  

   우분투 가상머신을 생성해준다.

   azure는 가상머신을 만들기만 하면 기타 다른 리소스를 자동으로 생성해주기 때문에 간편하다.

2. svn server는 기본적으로 3690포트를 사용하므로 해당 포트를 열어주어야한다.

   가상 머신의 네트워크 탭에서 인바운드 보안규칙을 추가한다.

   ![10 (1)](https://user-images.githubusercontent.com/63279334/126310352-853199a2-b9d2-464b-8aeb-8464d4fc496f.png)

   간편하도록 모든 ip와 포트를 열어주었다.

3. 생성한 가상머신의 외부 ip로 접속한 접속한다.

   ![5 (2)](https://user-images.githubusercontent.com/63279334/126310360-4f0f0358-0f9c-4311-89df-ab0666f6970b.png)

4. 이후 root계정으로 변경하고 `sudo su` 패키지를 업데이트한다. `apt-get update`
5. 그 다음 svn을 설치한다. `apt-get install subversion`
6. 이후 원하는 디렉토리를 생성하고,

   `mkdir -p /home/svn/repos`

   해당 디렉토리에 repository를 생성한다.

   `svnadmin create /home/svn/repos/test`

   이후 해당 repository로 이동한다.

   `cd /home/svn/repos/test`

   ![6 (2)](https://user-images.githubusercontent.com/63279334/126310369-47239e94-620f-419e-a6f7-5ee774da021a.png)


7. 이후 익명사용자가 접근할 수 있고, 파일을 작성할 수 있도록 설정을 변경한다.

   `cd conf`

   `vi svnserve.conf`

   ![7 (1)](https://user-images.githubusercontent.com/63279334/126310377-45f98fb4-e9a1-4247-98ab-248e4093905d.png)


8. 이후 svn을 사용할 수 있는 계정을 설정해준다.

   `vi passwd`

   현재 repository를 사용할 수 있는 user와 passwd를 설정한다.

  ![8 (2)](https://user-images.githubusercontent.com/63279334/126310390-b633a8a5-86fa-4163-862a-e98ed0c30048.png)

9. 서버를 실행한다.

   `svnserve -d -r /home/svn/repos/`

   ![9 (1)](https://user-images.githubusercontent.com/63279334/126310403-44f38cd0-e299-4390-acf7-22a5ffa3f18c.png)


10. 서버세팅이 완성되었다.
11. 이제 로컬 환경에서 해당 remote repository와의 연결을 수립한다.

    `svn://<가상머신 외부ip>/<생성한 저장소>`

   ![11 (2)](https://user-images.githubusercontent.com/63279334/126310430-71907b0c-0a8a-4e02-85a4-325daa4036b5.png)


12. 그리고 받아온 저장소 `test`에서 파일을 새롭게 `commit`한다.

    ![12](https://user-images.githubusercontent.com/63279334/126310441-90830dd0-4787-4faa-9a3e-6e6e1338ec9c.png)


13. 이제 새롭게 받은 저장소 `test2` 에서 remote repository에 업로드한 내용을 그대로 받아볼 수 있다.

    ![13](https://user-images.githubusercontent.com/63279334/126310449-d32490d0-e465-4741-b4a7-c54698c6ee44.png)

