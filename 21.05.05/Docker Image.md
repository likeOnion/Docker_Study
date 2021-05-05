관련 명령어
---
|명령어|내용|비고|
|:---:|:---:|:---:|
`docker search`|이미지 이름으로 이미지 검색 가능|
`docker hub`|git hub와 비슷함, 도커의 이미지들을 공유하는 공간|
`docker commit (옵션) 컨테이너 (저장소:태그)`|이미지 커밋|-a 는 작성자, -m 은 메모
`docker images`|로컬에 설치된 이미지 조회|
`docker inspect`|레이어 확인 가능|레이어는 변경사항이 저장되는 층(?) 같은 거라고 생각하면 됨, 이미지를 변경할 때마다 레이어가 추가됨
`docker history`|레이어 메티데이터 확인 가능|
`docker rmi (이미지)`|이미지 삭제|
`docker save (옵션)`|이미지 저장|-o 저장할 이름
`docker load (옵션)`|이미지 로드|-i 로드할 파일
`docker tag (기존 이름) (새 이름)`|이름 변경|기존 이름의 이미지를 변경하는 게 아니라 같은 내용의 새 이름을 가진 이미지 생성
`docker push/pull`|이미지 업로드/다운로드|
  
기타 용어 정리  
> 저장소 웹 축 : 저장소에 이미지가 push 될 때 특정 URL로 http 요청을 전송하도록 하는 기능  
> yml : 야믈 파일이라고 부름. 레지스트리 컨테이너의 환경 변수 설정해 놓은 파일  
  
[커밋 연습한 이미지 저장소](https://hub.docker.com/repository/docker/ijh4565/commit_test)
