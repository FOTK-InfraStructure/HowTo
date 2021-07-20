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

   ![https://s3-us-west-2.amazonaws.com/secure.notion-static.com/deb7a410-8e37-44f1-be4c-f91c141046b2/2.png](https://s3-us-west-2.amazonaws.com/secure.notion-static.com/deb7a410-8e37-44f1-be4c-f91c141046b2/2.png)

   userB

   ![https://s3-us-west-2.amazonaws.com/secure.notion-static.com/e07522cf-1e69-4356-988d-17b1af7a994f/3.png](https://s3-us-west-2.amazonaws.com/secure.notion-static.com/e07522cf-1e69-4356-988d-17b1af7a994f/3.png)

2. user A가 먼저 commit을 하고 user B가 이후에 commit을 한다.
3. 이 경우 user B에게 `confit` 가 발생한다.

   ![https://s3-us-west-2.amazonaws.com/secure.notion-static.com/eed09e67-25fc-4db9-9985-1ab4e72c37bb/5.png](https://s3-us-west-2.amazonaws.com/secure.notion-static.com/eed09e67-25fc-4db9-9985-1ab4e72c37bb/5.png)

   confict 부분을 더블클릭한다.

4. 어떤 부분에서 충돌이 났는지를 보여주는 화면이 나온다.

   ![https://s3-us-west-2.amazonaws.com/secure.notion-static.com/fdc015e5-a590-4a5b-9175-762b11449ea1/6.png](https://s3-us-west-2.amazonaws.com/secure.notion-static.com/fdc015e5-a590-4a5b-9175-762b11449ea1/6.png)

5. 이 화면에서 내 파일을 사용해서 상대방의 파일을 덮을지, 상대방의 파일을 사용해서 내 파일을 덮을지 결정할 수 있다.

   < 상대방의 파일로 내 파일을 덮는 경우 >

   ![https://s3-us-west-2.amazonaws.com/secure.notion-static.com/a5674b84-8c32-4cbf-b3ce-e97753c05548/7.png](https://s3-us-west-2.amazonaws.com/secure.notion-static.com/a5674b84-8c32-4cbf-b3ce-e97753c05548/7.png)

   < 내 파일로 상대방의 파일을 덮는 경우 >

   ![https://s3-us-west-2.amazonaws.com/secure.notion-static.com/cdb59159-7bb5-4a34-aacd-9d5dfcf50b5b/8.png](https://s3-us-west-2.amazonaws.com/secure.notion-static.com/cdb59159-7bb5-4a34-aacd-9d5dfcf50b5b/8.png)

6. 내 파일로 상대방의 파일을 덮었다.

   ![https://s3-us-west-2.amazonaws.com/secure.notion-static.com/415e9c61-cdf0-4059-9132-c1e1b37a2de7/9.png](https://s3-us-west-2.amazonaws.com/secure.notion-static.com/415e9c61-cdf0-4059-9132-c1e1b37a2de7/9.png)

   맨 아래에 합쳐진 파일에서 내 파일의 내용으로 덮인 것을 확인 할 수 있다.

   그리고 `Mark as resolved` 를 클릭하여 내용을 확인하고 `save` 한다.

7. 이제 repository에는 내가 수정한 내용으로 파일이 올라가 있는 상태이다.
8. user A를 update하면 수정한 파일의 내용으로 변한것을 확인할 수 있다.

   ![https://s3-us-west-2.amazonaws.com/secure.notion-static.com/77b20883-1a2c-4109-b77e-f2f1249ddac9/11.png](https://s3-us-west-2.amazonaws.com/secure.notion-static.com/77b20883-1a2c-4109-b77e-f2f1249ddac9/11.png)

### 저장소 이동하기

1. `testRepo`라는 저장소가 존재하다가 모종의 이유로 사라졌다고 하자.

   ![https://s3-us-west-2.amazonaws.com/secure.notion-static.com/b47d1f1b-bcf4-4021-85f2-72e2305d719c/2.png](https://s3-us-west-2.amazonaws.com/secure.notion-static.com/b47d1f1b-bcf4-4021-85f2-72e2305d719c/2.png)

   ![https://s3-us-west-2.amazonaws.com/secure.notion-static.com/e92de171-95eb-43db-ac68-14c2d7403ef0/3.png](https://s3-us-west-2.amazonaws.com/secure.notion-static.com/e92de171-95eb-43db-ac68-14c2d7403ef0/3.png)

   이런 사실을 모르고 userA가 자신의 변경 사항을 저장소에 반영하려고 하면 저장소에 연결할 수 없다는 문제가 발생한다.

   ![https://s3-us-west-2.amazonaws.com/secure.notion-static.com/929318de-15c7-4e75-a67c-f78e9b7a323b/4.png](https://s3-us-west-2.amazonaws.com/secure.notion-static.com/929318de-15c7-4e75-a67c-f78e9b7a323b/4.png)

2. 우선 새로운 저장소를 생성한다.

   ![https://s3-us-west-2.amazonaws.com/secure.notion-static.com/f708dad8-0d51-4779-a0f6-c930103b2a8e/5.png](https://s3-us-west-2.amazonaws.com/secure.notion-static.com/f708dad8-0d51-4779-a0f6-c930103b2a8e/5.png)

   `anotherRepo` 라는 저장소를 새롭게 만든다.

3. svn엔 저장소를 이동하는 기능인 `relocate` 가 존재한다.

   ![https://s3-us-west-2.amazonaws.com/secure.notion-static.com/1e7259e4-a079-4ded-a0f3-a6c34b9ff412/11.png](https://s3-us-west-2.amazonaws.com/secure.notion-static.com/1e7259e4-a079-4ded-a0f3-a6c34b9ff412/11.png)

4. 하지만 기존의 저장소와 새로운 저장소의 uuid가 다르다는 이유로 relocate를 활용할 수가 없다.

   ![https://s3-us-west-2.amazonaws.com/secure.notion-static.com/f7a0a487-8fe4-4aec-ac60-0b168fc7eb29/4.png](https://s3-us-west-2.amazonaws.com/secure.notion-static.com/f7a0a487-8fe4-4aec-ac60-0b168fc7eb29/4.png)

5. 그래서 `anotherRepo -> db -> uuid` 파일에서 기존 프로젝트의 uuid와 같도록 `anotherRepo` 의 uuid를 수정한다.

   ![https://s3-us-west-2.amazonaws.com/secure.notion-static.com/754ebb35-fcd6-40ae-8471-e5937f59a911/5.png](https://s3-us-west-2.amazonaws.com/secure.notion-static.com/754ebb35-fcd6-40ae-8471-e5937f59a911/5.png)

6. 다시 `relocate` 를 실행하면 정상적으로 저장소가 이동됐다는 메시지가 나온다.

   ![https://s3-us-west-2.amazonaws.com/secure.notion-static.com/6f48f82c-3420-4d6e-bf25-05774d8bbe7f/6.png](https://s3-us-west-2.amazonaws.com/secure.notion-static.com/6f48f82c-3420-4d6e-bf25-05774d8bbe7f/6.png)

7. 이후 파일을 변경하고 commit을 한다.
8. 하지만 커밋이 정상적으로 되지 않는다....

   ![https://s3-us-west-2.amazonaws.com/secure.notion-static.com/e70cb53a-83e8-4b36-916f-abb0da641849/8.png](https://s3-us-west-2.amazonaws.com/secure.notion-static.com/e70cb53a-83e8-4b36-916f-abb0da641849/8.png)

9. 따라서 수동으로 다른 방법을 사용해야한다.

   기존의 저장소에서 `export` 를 통해 기존의 내용들을 추출한다.

   ![https://s3-us-west-2.amazonaws.com/secure.notion-static.com/214956da-4ac5-4823-b4a3-1722a79b3423/6.png](https://s3-us-west-2.amazonaws.com/secure.notion-static.com/214956da-4ac5-4823-b4a3-1722a79b3423/6.png)

   아래와 같은 디렉토리들이 추출된다.

   ![https://s3-us-west-2.amazonaws.com/secure.notion-static.com/a0047954-6d63-464c-a1ac-b4203a1546d5/7.png](https://s3-us-west-2.amazonaws.com/secure.notion-static.com/a0047954-6d63-464c-a1ac-b4203a1546d5/7.png)

10. 추출된 디렉토리들을 새롭게 생성한 `anotherRepo` 에 넣어주면 저장소를 이동시킬 수 있다.

    ![https://s3-us-west-2.amazonaws.com/secure.notion-static.com/76c4dd9d-bcf8-4728-bc50-46832fc83ac7/8.png](https://s3-us-west-2.amazonaws.com/secure.notion-static.com/76c4dd9d-bcf8-4728-bc50-46832fc83ac7/8.png)

    ![https://s3-us-west-2.amazonaws.com/secure.notion-static.com/9a84368f-a35c-4262-84a0-ae6e4cb6901d/9.png](https://s3-us-west-2.amazonaws.com/secure.notion-static.com/9a84368f-a35c-4262-84a0-ae6e4cb6901d/9.png)

11. `anotherRepo` 를 확인해보면 기존의 저장소의 내용을 모두 가져온 것을 볼 수 있다.

    ![https://s3-us-west-2.amazonaws.com/secure.notion-static.com/dbbeee2c-138e-46ba-8ee2-45158de1be31/10.png](https://s3-us-west-2.amazonaws.com/secure.notion-static.com/dbbeee2c-138e-46ba-8ee2-45158de1be31/10.png)

    ![https://s3-us-west-2.amazonaws.com/secure.notion-static.com/bbc62f99-103b-40fa-acd9-c91bd51f0b89/11.png](https://s3-us-west-2.amazonaws.com/secure.notion-static.com/bbc62f99-103b-40fa-acd9-c91bd51f0b89/11.png)

12. 하지만 이 경우에도 기존에 작업하던 디렉토리에서 commit은 불가능하다.
13. 따라서 새롭게 생성한 저장소로 다시 checkout을 통해 작업 디렉토리를 생성한 후 작업을 이어나가야 한다.

    ![https://s3-us-west-2.amazonaws.com/secure.notion-static.com/30b12b72-8096-41e4-b064-85a0ce7ecd80/15.png](https://s3-us-west-2.amazonaws.com/secure.notion-static.com/30b12b72-8096-41e4-b064-85a0ce7ecd80/15.png)

### 외부저장소에서 사용하기

1. azure의 무료계정을 활용해서 remote svn 서버를 생성할 것이다.

   ![https://s3-us-west-2.amazonaws.com/secure.notion-static.com/0383a059-8765-4f34-9304-fe1903f798ff/3.png](https://s3-us-west-2.amazonaws.com/secure.notion-static.com/0383a059-8765-4f34-9304-fe1903f798ff/3.png)

   ![https://s3-us-west-2.amazonaws.com/secure.notion-static.com/da99a1cd-3e4b-4b13-accc-83c087746f2d/4.png](https://s3-us-west-2.amazonaws.com/secure.notion-static.com/da99a1cd-3e4b-4b13-accc-83c087746f2d/4.png)

   우분투 가상머신을 생성해준다.

   azure는 가상머신을 만들기만 하면 기타 다른 리소스를 자동으로 생성해주기 때문에 간편하다.

2. svn server는 기본적으로 3690포트를 사용하므로 해당 포트를 열어주어야한다.

   가상 머신의 네트워크 탭에서 인바운드 보안규칙을 추가한다.

   ![https://s3-us-west-2.amazonaws.com/secure.notion-static.com/1c6a4c42-95c0-426c-967a-b3034f12b868/10.png](https://s3-us-west-2.amazonaws.com/secure.notion-static.com/1c6a4c42-95c0-426c-967a-b3034f12b868/10.png)

   간편하도록 모든 ip와 포트를 열어주었다.

3. 생성한 가상머신의 외부 ip로 접속한 접속한다.

   ![https://s3-us-west-2.amazonaws.com/secure.notion-static.com/6aea6a41-6d75-49f5-8ab9-09ec448ec22d/5.png](https://s3-us-west-2.amazonaws.com/secure.notion-static.com/6aea6a41-6d75-49f5-8ab9-09ec448ec22d/5.png)

4. 이후 root계정으로 변경하고 `sudo su` 패키지를 업데이트한다. `apt-get update`
5. 그 다음 svn을 설치한다. `apt-get install subversion`
6. 이후 원하는 디렉토리를 생성하고,

   `mkdir -p /home/svn/repos`

   해당 디렉토리에 repository를 생성한다.

   `svnadmin create /home/svn/repos/test`

   이후 해당 repository로 이동한다.

   `cd /home/svn/repos/test`

   ![https://s3-us-west-2.amazonaws.com/secure.notion-static.com/7fc0199d-f623-4617-b617-b522321165d8/6.png](https://s3-us-west-2.amazonaws.com/secure.notion-static.com/7fc0199d-f623-4617-b617-b522321165d8/6.png)

7. 이후 익명사용자가 접근할 수 있고, 파일을 작성할 수 있도록 설정을 변경한다.

   `cd conf`

   `vi svnserve.conf`

   ![https://s3-us-west-2.amazonaws.com/secure.notion-static.com/0d7384ff-ea86-421e-a206-29af9095f8ad/7.png](https://s3-us-west-2.amazonaws.com/secure.notion-static.com/0d7384ff-ea86-421e-a206-29af9095f8ad/7.png)

8. 이후 svn을 사용할 수 있는 계정을 설정해준다.

   `vi passwd`

   현재 repository를 사용할 수 있는 user와 passwd를 설정한다.

   ![https://s3-us-west-2.amazonaws.com/secure.notion-static.com/8f000dcd-43c3-4583-831b-c20786ac634c/8.png](https://s3-us-west-2.amazonaws.com/secure.notion-static.com/8f000dcd-43c3-4583-831b-c20786ac634c/8.png)

9. 서버를 실행한다.

   `svnserve -d -r /home/svn/repos/`

   ![https://s3-us-west-2.amazonaws.com/secure.notion-static.com/c64d02d4-e4fe-47eb-a4f1-67d83f627c41/9.png](https://s3-us-west-2.amazonaws.com/secure.notion-static.com/c64d02d4-e4fe-47eb-a4f1-67d83f627c41/9.png)

10. 서버세팅이 완성되었다.
11. 이제 로컬 환경에서 해당 remote repository와의 연결을 수립한다.

    `svn://<가상머신 외부ip>/<생성한 저장소>`

    ![https://s3-us-west-2.amazonaws.com/secure.notion-static.com/a09463e6-b7b6-4ce3-9a0f-3fa805c6431b/11.png](https://s3-us-west-2.amazonaws.com/secure.notion-static.com/a09463e6-b7b6-4ce3-9a0f-3fa805c6431b/11.png)

12. 그리고 받아온 저장소 `test`에서 파일을 새롭게 `commit`한다.

    ![https://s3-us-west-2.amazonaws.com/secure.notion-static.com/d869d0bd-e1e6-4983-8f16-b07343e4884f/12.png](https://s3-us-west-2.amazonaws.com/secure.notion-static.com/d869d0bd-e1e6-4983-8f16-b07343e4884f/12.png)

13. 이제 새롭게 받은 저장소 `test2` 에서 remote repository에 업로드한 내용을 그대로 받아볼 수 있다.

    ![https://s3-us-west-2.amazonaws.com/secure.notion-static.com/ae59b2d3-706c-47c5-9e04-077de89b7074/13.png](https://s3-us-west-2.amazonaws.com/secure.notion-static.com/ae59b2d3-706c-47c5-9e04-077de89b7074/13.png)
